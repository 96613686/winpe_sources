# mregGetIdFromStringId

- ea: `0x180008be0`
- end: `0x180008ddf`
- name: `mregGetIdFromStringId`
- size: `511`
- prototype: ``
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x180007dd0`
- `0x1800087a0`
- `0x180008834`
- `0x1800094f4`
- `0x180009d20`
- `0x180009d64`
- `0x180009d9c`
- `0x18000f1c4`
- `0x18000f1fc`
- `0x18000f498`

## callees

- `0x180008be0`
- `0x180008df0`
- `0x180008ee0`
- `0x18001102a`
- `0x180011d6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180008cb9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180008cb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008d27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008d27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008c20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008c20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c8a`

## pseudocode

```c
__int64 __fastcall mregGetIdFromStringId(struct _MMDRV **a1, const unsigned __int16 *a2, unsigned int *a3)
{
  struct _MMDRV *v3; // rsi
  wchar_t *v7; // rax
  wchar_t *v8; // rdi
  unsigned int v9; // ebx
  int v11; // eax
  unsigned int v12; // r8d
  unsigned __int16 *v13; // r10
  wchar_t v14; // cx
  wchar_t *v15; // rdx
  struct _MMDRV *v16; // rax
  unsigned int i; // edx
  unsigned int v18; // eax
  unsigned int v19; // eax
  struct _MMDRV *v20[5]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v21; // [rsp+70h] [rbp+18h] BYREF
  wchar_t *EndPtr; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  v20[0] = 0;
  v21 = 0;
  if ( a3 && a2 )
  {
    EnterCriticalSection(&NumDevsCritSec);
    if ( !dword_18002C568 )
    {
      memset_0(&StringIdDict, 0, 0x3F8u);
      dword_18002C568 = 1;
    }
    v7 = lstrDuplicateW(a2);
    v8 = v7;
    if ( !v7 )
    {
      v9 = 7;
      goto LABEL_7;
    }
    EndPtr = v7;
    v11 = wcstol(v7, &EndPtr, 16);
    if ( *EndPtr != 58 )
      goto LABEL_17;
    v12 = 0;
    *EndPtr = 0;
    v13 = ++EndPtr;
    v14 = *v8;
    if ( *v8 )
    {
      v15 = v8;
      do
      {
        ++v15;
        v12 = (v14 & 0xFFDF) + 101 * v12;
        v14 = *v15;
      }
      while ( *v15 );
    }
    if ( v11 )
    {
      if ( v11 != 1 )
      {
LABEL_17:
        v9 = 11;
        goto LABEL_18;
      }
      v18 = StringIdDict_SearchType0And1(1u, v13, v12, v20, &v21);
      v3 = v20[0];
      v9 = v18;
    }
    else
    {
      v19 = StringIdDict_SearchType0And1(0, v13, v12, v20, &v21);
      v3 = v20[0];
      v9 = v19;
    }
LABEL_18:
    HeapFree(hHeap, 0, v8);
    if ( !v9 )
    {
      v16 = *a1;
      for ( i = v21; v16 != (struct _MMDRV *)a1; v16 = *(struct _MMDRV **)v16 )
      {
        if ( v16 == v3 )
          break;
        if ( (*((_BYTE *)v16 + 112) & 2) == 0 )
          i += *((_DWORD *)v16 + 22);
      }
      *a3 = i;
      goto LABEL_10;
    }
LABEL_7:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c23b9cac3f383ee5edfc4d9869f3b1c0_Traceguids, v9);
LABEL_10:
    LeaveCriticalSection(&NumDevsCritSec);
    return v9;
  }
  return 11;
}

```

## disassembly

```asm
0x180008be0  mov     [rsp+arg_8], rbx
0x180008be5  push    rsi
0x180008be6  push    r14
0x180008be8  push    r15
0x180008bea  sub     rsp, 40h
0x180008bee  xor     esi, esi
0x180008bf0  mov     r14, r8
0x180008bf3  mov     [rsp+58h+var_28], rsi
0x180008bf8  mov     rbx, rdx
0x180008bfb  mov     [rsp+58h+arg_10], esi
0x180008bff  mov     r15, rcx
0x180008c02  test    r8, r8
0x180008c05  jz      loc_180008DD5
0x180008c0b  test    rdx, rdx
0x180008c0e  jz      loc_180008DD5
0x180008c14  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180008c1b  mov     [rsp+58h+arg_0], rdi
0x180008c20  call    cs:__imp_EnterCriticalSection
0x180008c26  cmp     cs:dword_18002C568, esi
0x180008c2c  jz      loc_180008D73
0x180008c32  mov     rcx, rbx; unsigned __int16 *
0x180008c35  call    ?lstrDuplicateW@@YAPEAGPEBG@Z; lstrDuplicateW(ushort const *)
0x180008c3a  mov     rdi, rax
0x180008c3d  test    rax, rax
0x180008c40  jnz     short loc_180008CA6
0x180008c42  mov     ebx, 7
0x180008c47  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c4e  lea     rax, WPP_GLOBAL_Control
0x180008c55  cmp     rcx, rax
0x180008c58  jz      short loc_180008C83
0x180008c5a  test    dword ptr [rcx+1Ch], 400000h
0x180008c61  jz      short loc_180008C7B
0x180008c63  mov     rcx, [rcx+10h]
0x180008c67  lea     r8, WPP_c23b9cac3f383ee5edfc4d9869f3b1c0_Traceguids
0x180008c6e  mov     edx, 0Bh
0x180008c73  mov     r9d, ebx
0x180008c76  call    WPP_SF_d
0x180008c7b  test    ebx, ebx
0x180008c7d  jz      loc_180008D35
0x180008c83  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180008c8a  call    cs:__imp_LeaveCriticalSection
0x180008c90  mov     rdi, [rsp+58h+arg_0]
0x180008c95  mov     eax, ebx
0x180008c97  mov     rbx, [rsp+58h+arg_8]
0x180008c9c  add     rsp, 40h
0x180008ca0  pop     r15
0x180008ca2  pop     r14
0x180008ca4  pop     rsi
0x180008ca5  retn
0x180008ca6  mov     r8d, 10h; Radix
0x180008cac  mov     [rsp+58h+EndPtr], rdi
0x180008cb1  lea     rdx, [rsp+58h+EndPtr]; EndPtr
0x180008cb6  mov     rcx, rdi; String
0x180008cb9  call    cs:__imp_wcstol
0x180008cbf  mov     rdx, [rsp+58h+EndPtr]
0x180008cc4  cmp     word ptr [rdx], 3Ah ; ':'
0x180008cc8  jnz     short loc_180008D16
0x180008cca  xor     ecx, ecx
0x180008ccc  xor     r8d, r8d
0x180008ccf  mov     [rdx], cx
0x180008cd2  mov     r10, [rsp+58h+EndPtr]
0x180008cd7  add     r10, 2
0x180008cdb  mov     [rsp+58h+EndPtr], r10
0x180008ce0  movzx   ecx, word ptr [rdi]
0x180008ce3  test    cx, cx
0x180008ce6  jz      short loc_180008D09
0x180008ce8  mov     rdx, rdi
0x180008ceb  nop     dword ptr [rax+rax+00h]
0x180008cf0  and     ecx, 0FFDFh
0x180008cf6  imul    r8d, 65h ; 'e'
0x180008cfa  lea     rdx, [rdx+2]
0x180008cfe  add     r8d, ecx; unsigned int
0x180008d01  movzx   ecx, word ptr [rdx]
0x180008d04  test    cx, cx
0x180008d07  jnz     short loc_180008CF0
0x180008d09  test    eax, eax
0x180008d0b  jz      loc_180008D96
0x180008d11  cmp     eax, 1
0x180008d14  jz      short loc_180008D4E
0x180008d16  mov     ebx, 0Bh
0x180008d1b  mov     rcx, cs:hHeap; hHeap
0x180008d22  mov     r8, rdi; lpMem
0x180008d25  xor     edx, edx; dwFlags
0x180008d27  call    cs:__imp_HeapFree
0x180008d2d  test    ebx, ebx
0x180008d2f  jnz     loc_180008C47
0x180008d35  mov     rax, [r15]
0x180008d38  mov     edx, [rsp+58h+arg_10]
0x180008d3c  cmp     rax, r15
0x180008d3f  jz      short loc_180008D46
0x180008d41  cmp     rax, rsi
0x180008d44  jnz     short loc_180008DBB
0x180008d46  mov     [r14], edx
0x180008d49  jmp     loc_180008C83
0x180008d4e  lea     rax, [rsp+58h+arg_10]
0x180008d53  mov     rdx, r10; unsigned __int16 *
0x180008d56  lea     r9, [rsp+58h+var_28]; struct _MMDRV **
0x180008d5b  mov     [rsp+58h+var_38], rax; unsigned int *
0x180008d60  mov     ecx, 1; unsigned int
0x180008d65  call    ?StringIdDict_SearchType0And1@@YAIKPEAGKPEAPEAU_MMDRV@@PEAI@Z; StringIdDict_SearchType0And1(ulong,ushort *,ulong,_MMDRV * *,uint *)
0x180008d6a  mov     rsi, [rsp+58h+var_28]
0x180008d6f  mov     ebx, eax
0x180008d71  jmp     short loc_180008D1B
0x180008d73  xor     edx, edx; Val
0x180008d75  lea     rcx, ?StringIdDict@@3PAPEAU_MMDRV@@A; void *
0x180008d7c  mov     r8d, 3F8h; Size
0x180008d82  call    memset_0
0x180008d87  mov     cs:dword_18002C568, 1
0x180008d91  jmp     loc_180008C32
0x180008d96  lea     rax, [rsp+58h+arg_10]
0x180008d9b  mov     rdx, r10; unsigned __int16 *
0x180008d9e  lea     r9, [rsp+58h+var_28]; struct _MMDRV **
0x180008da3  mov     [rsp+58h+var_38], rax; unsigned int *
0x180008da8  xor     ecx, ecx; unsigned int
0x180008daa  call    ?StringIdDict_SearchType0And1@@YAIKPEAGKPEAPEAU_MMDRV@@PEAI@Z; StringIdDict_SearchType0And1(ulong,ushort *,ulong,_MMDRV * *,uint *)
0x180008daf  mov     rsi, [rsp+58h+var_28]
0x180008db4  mov     ebx, eax
0x180008db6  jmp     loc_180008D1B
0x180008dbb  test    byte ptr [rax+70h], 2
0x180008dbf  jnz     short loc_180008DC4
0x180008dc1  add     edx, [rax+58h]
0x180008dc4  mov     rax, [rax]
0x180008dc7  cmp     rax, r15
0x180008dca  jnz     loc_180008D41
0x180008dd0  jmp     loc_180008D46
0x180008dd5  mov     eax, 0Bh
0x180008dda  jmp     loc_180008C97
```
