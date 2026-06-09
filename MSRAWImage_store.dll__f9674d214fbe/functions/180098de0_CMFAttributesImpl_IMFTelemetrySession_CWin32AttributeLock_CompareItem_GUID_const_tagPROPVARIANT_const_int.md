# CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::CompareItem(_GUID const &,tagPROPVARIANT const &,int *)

- ea: `0x180098de0`
- end: `0x180098f28`
- name: `?CompareItem@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@AEBUtagPROPVARIANT@@PEAH@Z`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180098de0`
- `0x18009e6d0`
- `0x1800b0ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098efe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098efe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098e09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098e09`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::CompareItem(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int *a4)
{
  __int64 Item; // rax
  int v9; // ebx
  __int64 v10; // r10
  __int16 v11; // cx
  unsigned int v12; // eax
  bool v13; // zf
  _QWORD *v14; // rcx
  _QWORD *v15; // rdx
  __int64 v16; // rax
  unsigned __int16 *v17; // rax
  __int64 v18; // r8
  int v19; // edx
  int v20; // ecx

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_FindItem(a1, a2);
  v9 = 0;
  v10 = Item;
  if ( !Item )
    goto LABEL_24;
  v11 = *(_WORD *)Item;
  if ( *(_WORD *)a3 != *(_WORD *)Item )
    goto LABEL_24;
  switch ( v11 )
  {
    case 5:
      v13 = *(double *)(Item + 8) == *(double *)(a3 + 8);
      break;
    case 13:
      goto LABEL_23;
    case 19:
      v13 = *(_DWORD *)(Item + 8) == *(_DWORD *)(a3 + 8);
      break;
    case 21:
      v13 = *(_QWORD *)(Item + 8) == *(_QWORD *)(a3 + 8);
      break;
    case 31:
      v17 = *(unsigned __int16 **)(Item + 8);
      v18 = *(_QWORD *)(a3 + 8) - (_QWORD)v17;
      do
      {
        v19 = *(unsigned __int16 *)((char *)v17 + v18);
        v20 = *v17 - v19;
        if ( v20 )
          break;
        ++v17;
      }
      while ( v19 );
      v13 = v20 == 0;
      break;
    case 72:
      v14 = *(_QWORD **)(Item + 8);
      v15 = *(_QWORD **)(a3 + 8);
      v16 = *v14 - *v15;
      if ( *v14 == *v15 )
        v16 = v14[1] - v15[1];
      v13 = v16 == 0;
      break;
    case 4113:
      v12 = *(_DWORD *)(Item + 8);
      if ( v12 != *(_DWORD *)(a3 + 8) )
        goto LABEL_24;
      v13 = memcmp(*(const void **)(v10 + 16), *(const void **)(a3 + 16), v12) == 0;
      break;
    default:
LABEL_23:
      v9 = 1;
      goto LABEL_24;
  }
  if ( v13 )
    goto LABEL_23;
LABEL_24:
  *a4 = v9;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return 0;
}

```

## disassembly

```asm
0x180098de0  mov     rax, rsp
0x180098de3  mov     [rax+8], rbx
0x180098de7  mov     [rax+10h], rbp
0x180098deb  mov     [rax+18h], rsi
0x180098def  mov     [rax+20h], rdi
0x180098df3  push    r14
0x180098df5  sub     rsp, 20h
0x180098df9  mov     rdi, rcx
0x180098dfc  mov     r14, r9
0x180098dff  add     rcx, 8; lpCriticalSection
0x180098e03  mov     rsi, r8
0x180098e06  mov     rbx, rdx
0x180098e09  call    cs:__imp_EnterCriticalSection
0x180098e10  nop     dword ptr [rax+rax+00h]
0x180098e15  mov     rdx, rbx
0x180098e18  mov     rcx, rdi
0x180098e1b  call    ?_FindItem@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_FindItem(_GUID const &)
0x180098e20  xor     ebx, ebx
0x180098e22  mov     r10, rax
0x180098e25  test    rax, rax
0x180098e28  jz      loc_180098EF7
0x180098e2e  movzx   ecx, word ptr [rax]
0x180098e31  cmp     [rsi], cx
0x180098e34  jnz     loc_180098EF7
0x180098e3a  cmp     cx, 5
0x180098e3e  jz      loc_180098EE4
0x180098e44  cmp     cx, 0Dh
0x180098e48  jz      loc_180098EF2
0x180098e4e  cmp     cx, 13h
0x180098e52  jz      loc_180098EDB
0x180098e58  cmp     cx, 15h
0x180098e5c  jz      short loc_180098ED1
0x180098e5e  cmp     cx, 1Fh
0x180098e62  jz      short loc_180098EAE
0x180098e64  cmp     cx, 48h ; 'H'
0x180098e68  jz      short loc_180098E91
0x180098e6a  mov     eax, 1011h
0x180098e6f  cmp     cx, ax
0x180098e72  jnz     short loc_180098EF2
0x180098e74  mov     eax, [r10+8]
0x180098e78  cmp     eax, [rsi+8]
0x180098e7b  jnz     short loc_180098EF7
0x180098e7d  mov     rdx, [rsi+10h]; Buf2
0x180098e81  mov     r8d, eax; Size
0x180098e84  mov     rcx, [r10+10h]; Buf1
0x180098e88  call    memcmp
0x180098e8d  test    eax, eax
0x180098e8f  jmp     short loc_180098EF0
0x180098e91  mov     rcx, [rax+8]
0x180098e95  mov     rdx, [rsi+8]
0x180098e99  mov     rax, [rcx]
0x180098e9c  sub     rax, [rdx]
0x180098e9f  jnz     short loc_180098EA9
0x180098ea1  mov     rax, [rcx+8]
0x180098ea5  sub     rax, [rdx+8]
0x180098ea9  test    rax, rax
0x180098eac  jmp     short loc_180098EF0
0x180098eae  mov     rax, [rax+8]
0x180098eb2  mov     r8, [rsi+8]
0x180098eb6  sub     r8, rax
0x180098eb9  movzx   ecx, word ptr [rax]
0x180098ebc  movzx   edx, word ptr [rax+r8]
0x180098ec1  sub     ecx, edx
0x180098ec3  jnz     short loc_180098ECD
0x180098ec5  add     rax, 2
0x180098ec9  test    edx, edx
0x180098ecb  jnz     short loc_180098EB9
0x180098ecd  test    ecx, ecx
0x180098ecf  jmp     short loc_180098EF0
0x180098ed1  mov     rax, [rsi+8]
0x180098ed5  cmp     [r10+8], rax
0x180098ed9  jmp     short loc_180098EF0
0x180098edb  mov     eax, [rsi+8]
0x180098ede  cmp     [r10+8], eax
0x180098ee2  jmp     short loc_180098EF0
0x180098ee4  movsd   xmm0, qword ptr [rax+8]
0x180098ee9  ucomisd xmm0, qword ptr [rsi+8]
0x180098eee  jp      short loc_180098EF7
0x180098ef0  jnz     short loc_180098EF7
0x180098ef2  mov     ebx, 1
0x180098ef7  lea     rcx, [rdi+8]; lpCriticalSection
0x180098efb  mov     [r14], ebx
0x180098efe  call    cs:__imp_LeaveCriticalSection
0x180098f05  nop     dword ptr [rax+rax+00h]
0x180098f0a  mov     rbx, [rsp+28h+arg_0]
0x180098f0f  xor     eax, eax
0x180098f11  mov     rbp, [rsp+28h+arg_8]
0x180098f16  mov     rsi, [rsp+28h+arg_10]
0x180098f1b  mov     rdi, [rsp+28h+arg_18]
0x180098f20  add     rsp, 20h
0x180098f24  pop     r14
0x180098f26  retn
```
