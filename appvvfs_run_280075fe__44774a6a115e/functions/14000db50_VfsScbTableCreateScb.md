# VfsScbTableCreateScb

- ea: `0x14000db50`
- end: `0x14000dcca`
- name: `VfsScbTableCreateScb`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000f188`

## callees

- `0x14000d3b4`
- `0x14000db50`
- `0x140013b00`
- `0x140014000`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14000dc09`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14000dc09`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000dc78`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000dc78`
- `ntoskrnl!RtlCopySid` at `0x14000dbcc`
- `ntoskrnl!RtlCopySid` at `0x14000dbcc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000dc94`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000dc94`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000dc88`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000dc88`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000dbed`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000dbed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000dbdc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000dbdc`

## pseudocode

```c
__int64 __fastcall VfsScbTableCreateScb(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, _BYTE *a5)
{
  void *v8; // r8
  _OWORD *v9; // rax
  struct _ERESOURCE *v10; // rbx
  _QWORD *inserted; // rax
  _QWORD *v12; // rsi
  int v13; // ebx
  __int64 v14; // rcx
  unsigned __int8 NewElement[8]; // [rsp+20h] [rbp-81h] BYREF
  __int64 v17; // [rsp+28h] [rbp-79h] BYREF
  __int64 v18; // [rsp+30h] [rbp-71h]
  _OWORD Buffer[7]; // [rsp+40h] [rbp-61h] BYREF

  v18 = a1;
  memset(Buffer, 0, 0x64u);
  *a4 = 0;
  *a5 = 0;
  v8 = *(void **)(a3 + 8);
  NewElement[0] = 0;
  v17 = 0;
  v9 = *(_OWORD **)(a3 + 16);
  Buffer[0] = *v9;
  Buffer[1] = v9[1];
  RtlCopySid(0x44u, &Buffer[2], v8);
  v10 = *(struct _ERESOURCE **)(a2 + 8);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(v10, 1u);
  inserted = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(a2 + 16), Buffer, 0x64u, NewElement);
  v12 = inserted;
  if ( inserted )
  {
    if ( NewElement[0] )
    {
      v13 = VfsCreateScb(v18, (void *)a2, a3, &v17);
      if ( v13 < 0 )
      {
        RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a2 + 16), Buffer);
        goto LABEL_11;
      }
      v14 = v17;
      v12[14] = v17;
    }
    else
    {
      v14 = inserted[14];
      v13 = 0;
      if ( (*(_DWORD *)(v14 + 272) & 1) != 0 )
      {
        *a5 = 1;
        goto LABEL_11;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v14 + 276));
    }
    *a4 = v14;
    goto LABEL_11;
  }
  v13 = -1073741670;
LABEL_11:
  ExReleaseResourceLite(*(PERESOURCE *)(a2 + 8));
  KeLeaveCriticalRegion();
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000db50  mov     [rsp-8+arg_0], rbx
0x14000db55  push    rbp
0x14000db56  push    rsi
0x14000db57  push    rdi
0x14000db58  push    r12
0x14000db5a  push    r13
0x14000db5c  push    r14
0x14000db5e  push    r15
0x14000db60  lea     rbp, [rsp-1Fh]
0x14000db65  sub     rsp, 0C0h
0x14000db6c  mov     rax, cs:__security_cookie
0x14000db73  xor     rax, rsp
0x14000db76  mov     [rbp+4Fh+var_40], rax
0x14000db7a  mov     r15, [rbp+4Fh+arg_20]
0x14000db7e  mov     r13, r8
0x14000db81  mov     r14, rdx
0x14000db84  mov     [rbp+4Fh+var_C0], rcx
0x14000db88  mov     esi, 64h ; 'd'
0x14000db8d  lea     rcx, [rbp+4Fh+Buffer]; void *
0x14000db91  mov     r8d, esi; Size
0x14000db94  xor     edx, edx; Val
0x14000db96  mov     rdi, r9
0x14000db99  call    memset
0x14000db9e  xor     eax, eax
0x14000dba0  lea     rdx, [rbp+4Fh+DestinationSid]; DestinationSid
0x14000dba4  mov     [rdi], rax
0x14000dba7  lea     ecx, [rsi-20h]; DestinationSidLength
0x14000dbaa  mov     [r15], al
0x14000dbad  mov     r8, [r13+8]; SourceSid
0x14000dbb1  mov     [rsp+0F0h+NewElement], al
0x14000dbb5  mov     [rbp+4Fh+var_C8], rax
0x14000dbb9  mov     rax, [r13+10h]
0x14000dbbd  movups  xmm0, xmmword ptr [rax]
0x14000dbc0  movaps  [rbp+4Fh+Buffer], xmm0
0x14000dbc4  movups  xmm1, xmmword ptr [rax+10h]
0x14000dbc8  movaps  [rbp+4Fh+var_A0], xmm1
0x14000dbcc  call    cs:__imp_RtlCopySid
0x14000dbd3  nop     dword ptr [rax+rax+00h]
0x14000dbd8  mov     rbx, [r14+8]
0x14000dbdc  call    cs:__imp_KeEnterCriticalRegion
0x14000dbe3  nop     dword ptr [rax+rax+00h]
0x14000dbe8  mov     dl, 1; Wait
0x14000dbea  mov     rcx, rbx; Resource
0x14000dbed  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000dbf4  nop     dword ptr [rax+rax+00h]
0x14000dbf9  lea     r9, [rsp+0F0h+NewElement]; NewElement
0x14000dbfe  mov     r8d, esi; BufferSize
0x14000dc01  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x14000dc05  lea     rcx, [r14+10h]; Table
0x14000dc09  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14000dc10  nop     dword ptr [rax+rax+00h]
0x14000dc15  mov     rsi, rax
0x14000dc18  test    rax, rax
0x14000dc1b  jnz     short loc_14000DC24
0x14000dc1d  mov     ebx, 0C000009Ah
0x14000dc22  jmp     short loc_14000DC84
0x14000dc24  cmp     [rsp+0F0h+NewElement], 0
0x14000dc29  jnz     short loc_14000DC4A
0x14000dc2b  mov     rcx, [rax+70h]
0x14000dc2f  xor     ebx, ebx
0x14000dc31  mov     eax, [rcx+110h]
0x14000dc37  test    al, 1
0x14000dc39  jz      short loc_14000DC41
0x14000dc3b  mov     byte ptr [r15], 1
0x14000dc3f  jmp     short loc_14000DC84
0x14000dc41  lock inc dword ptr [rcx+114h]
0x14000dc48  jmp     short loc_14000DC6B
0x14000dc4a  mov     rcx, [rbp+4Fh+var_C0]
0x14000dc4e  lea     r9, [rbp+4Fh+var_C8]
0x14000dc52  mov     r8, r13
0x14000dc55  mov     rdx, r14
0x14000dc58  call    VfsCreateScb
0x14000dc5d  mov     ebx, eax
0x14000dc5f  test    eax, eax
0x14000dc61  js      short loc_14000DC70
0x14000dc63  mov     rcx, [rbp+4Fh+var_C8]
0x14000dc67  mov     [rsi+70h], rcx
0x14000dc6b  mov     [rdi], rcx
0x14000dc6e  jmp     short loc_14000DC84
0x14000dc70  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x14000dc74  lea     rcx, [r14+10h]; Table
0x14000dc78  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14000dc7f  nop     dword ptr [rax+rax+00h]
0x14000dc84  mov     rcx, [r14+8]; Resource
0x14000dc88  call    cs:__imp_ExReleaseResourceLite
0x14000dc8f  nop     dword ptr [rax+rax+00h]
0x14000dc94  call    cs:__imp_KeLeaveCriticalRegion
0x14000dc9b  nop     dword ptr [rax+rax+00h]
0x14000dca0  mov     eax, ebx
0x14000dca2  mov     rcx, [rbp+4Fh+var_40]
0x14000dca6  xor     rcx, rsp; StackCookie
0x14000dca9  call    __security_check_cookie
0x14000dcae  mov     rbx, [rsp+0F0h+arg_0]
0x14000dcb6  add     rsp, 0C0h
0x14000dcbd  pop     r15
0x14000dcbf  pop     r14
0x14000dcc1  pop     r13
0x14000dcc3  pop     r12
0x14000dcc5  pop     rdi
0x14000dcc6  pop     rsi
0x14000dcc7  pop     rbp
0x14000dcc8  retn
```
