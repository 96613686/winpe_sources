# MbbAllocMgrInitialize(ulong,ulong,ulong,MBB_ALLOC_FLAGS)

- ea: `0x14001deb0`
- end: `0x14001dfea`
- name: `?MbbAllocMgrInitialize@@YAPEAXKKKTMBB_ALLOC_FLAGS@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14001a2a4`
- `0x140023f4c`

## callees

- `0x14001dd20`
- `0x14001deb0`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001df3c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001df3c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001df74`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001df74`
- `ntoskrnl!ExAllocatePool2` at `0x14001ded6`
- `ntoskrnl!ExAllocatePool2` at `0x14001ded6`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001def5`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001def5`
- `NDIS!NdisGetVersion` at `0x14001df07`
- `NDIS!NdisGetVersion` at `0x14001df07`

## pseudocode

```c
__int64 __fastcall MbbAllocMgrInitialize(unsigned int a1, unsigned int a2, ULONG a3, int a4)
{
  __int64 v5; // rsi
  __int64 result; // rax
  __int64 v9; // rbp
  UINT Version; // eax
  __int64 v11; // rdi
  __int64 v12; // rsi
  unsigned int v13; // ebx
  _QWORD *v14; // rax
  _QWORD *v15; // rcx
  __int64 **v16; // rcx
  __int64 *v17; // rax

  v5 = a1;
  result = ExAllocatePool2(64, 192, 1683505741);
  v9 = result;
  if ( result )
  {
    KeInitializeSpinLock((PKSPIN_LOCK)(result + 128));
    Version = NdisGetVersion();
    ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v9, 0, 0, Version >= 0x6001E ? 0x200 : 0, v5 + 48, a3, 0);
    v11 = v9 + 144;
    *(_DWORD *)(v9 + 176) = a4;
    v12 = v9 + 160;
    *(_QWORD *)(v9 + 152) = v9 + 144;
    v13 = 0;
    *(_QWORD *)(v9 + 144) = v9 + 144;
    *(_QWORD *)(v9 + 168) = v9 + 160;
    *(_QWORD *)(v9 + 160) = v9 + 160;
    if ( a2 )
    {
      while ( 1 )
      {
        v14 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v9);
        if ( !v14 )
          break;
        v14[5] = v9;
        *((_BYTE *)v14 + 32) = 1;
        v15 = *(_QWORD **)(v9 + 152);
        if ( *v15 != v11
          || (*v14 = v11,
              v14[1] = v15,
              *v15 = v14,
              *(_QWORD *)(v9 + 152) = v14,
              v16 = *(__int64 ***)(v9 + 168),
              *v16 != (__int64 *)v12) )
        {
          __fastfail(3u);
        }
        v17 = v14 + 2;
        ++v13;
        v17[1] = (__int64)v16;
        *v17 = v12;
        *v16 = v17;
        *(_QWORD *)(v9 + 168) = v17;
        if ( v13 >= a2 )
          return v9;
      }
      MbbAllocMgrCleanup((char *)v9);
      return 0;
    }
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x14001deb0  push    rbx
0x14001deb2  push    rbp
0x14001deb3  push    rsi
0x14001deb4  push    rdi
0x14001deb5  push    r14
0x14001deb7  push    r15
0x14001deb9  sub     rsp, 48h
0x14001debd  mov     r14d, edx
0x14001dec0  mov     esi, ecx
0x14001dec2  mov     edx, 0C0h
0x14001dec7  mov     r15d, r8d
0x14001deca  mov     r8d, 6458424Dh
0x14001ded0  mov     ebx, r9d
0x14001ded3  lea     ecx, [rdx-80h]
0x14001ded6  call    cs:__imp_ExAllocatePool2
0x14001dedd  nop     dword ptr [rax+rax+00h]
0x14001dee2  mov     rbp, rax
0x14001dee5  test    rax, rax
0x14001dee8  jz      loc_14001DFDC
0x14001deee  lea     rcx, [rax+80h]; SpinLock
0x14001def5  call    cs:__imp_KeInitializeSpinLock
0x14001defc  nop     dword ptr [rax+rax+00h]
0x14001df01  xor     edi, edi
0x14001df03  add     rsi, 30h ; '0'
0x14001df07  call    cs:__imp_NdisGetVersion
0x14001df0e  nop     dword ptr [rax+rax+00h]
0x14001df13  mov     [rsp+78h+Depth], di; Depth
0x14001df18  mov     rcx, rbp; Lookaside
0x14001df1b  cmp     eax, 6001Eh
0x14001df20  mov     [rsp+78h+Tag], r15d; Tag
0x14001df25  mov     [rsp+78h+Size], rsi; Size
0x14001df2a  sbb     r9d, r9d
0x14001df2d  xor     r8d, r8d; Free
0x14001df30  not     r9d
0x14001df33  xor     edx, edx; Allocate
0x14001df35  and     r9d, 200h; Flags
0x14001df3c  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001df43  nop     dword ptr [rax+rax+00h]
0x14001df48  lea     rdi, [rbp+90h]
0x14001df4f  mov     [rbp+0B0h], ebx
0x14001df55  lea     rsi, [rbp+0A0h]
0x14001df5c  mov     [rdi+8], rdi
0x14001df60  xor     ebx, ebx
0x14001df62  mov     [rdi], rdi
0x14001df65  mov     [rsi+8], rsi
0x14001df69  mov     [rsi], rsi
0x14001df6c  test    r14d, r14d
0x14001df6f  jz      short loc_14001DFD9
0x14001df71  mov     rcx, rbp; Lookaside
0x14001df74  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001df7b  nop     dword ptr [rax+rax+00h]
0x14001df80  test    rax, rax
0x14001df83  jz      short loc_14001DFCF
0x14001df85  mov     [rax+28h], rbp
0x14001df89  mov     byte ptr [rax+20h], 1
0x14001df8d  mov     rcx, [rdi+8]
0x14001df91  cmp     [rcx], rdi
0x14001df94  jnz     short loc_14001DFC8
0x14001df96  mov     [rax], rdi
0x14001df99  mov     [rax+8], rcx
0x14001df9d  mov     [rcx], rax
0x14001dfa0  mov     [rdi+8], rax
0x14001dfa4  mov     rcx, [rsi+8]
0x14001dfa8  cmp     [rcx], rsi
0x14001dfab  jnz     short loc_14001DFC8
0x14001dfad  add     rax, 10h
0x14001dfb1  inc     ebx
0x14001dfb3  mov     [rax+8], rcx
0x14001dfb7  mov     [rax], rsi
0x14001dfba  mov     [rcx], rax
0x14001dfbd  mov     [rsi+8], rax
0x14001dfc1  cmp     ebx, r14d
0x14001dfc4  jb      short loc_14001DF71
0x14001dfc6  jmp     short loc_14001DFD9
0x14001dfc8  mov     ecx, 3
0x14001dfcd  int     29h; Win8: RtlFailFast(ecx)
0x14001dfcf  mov     rcx, rbp; P
0x14001dfd2  call    ?MbbAllocMgrCleanup@@YAXPEAX@Z; MbbAllocMgrCleanup(void *)
0x14001dfd7  xor     ebp, ebp
0x14001dfd9  mov     rax, rbp
0x14001dfdc  add     rsp, 48h
0x14001dfe0  pop     r15
0x14001dfe2  pop     r14
0x14001dfe4  pop     rdi
0x14001dfe5  pop     rsi
0x14001dfe6  pop     rbp
0x14001dfe7  pop     rbx
0x14001dfe8  retn
```
