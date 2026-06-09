# DSSGetSharedFileName(ushort const *,ushort * *)

- ea: `0x18000cfcc`
- end: `0x18000d0c7`
- name: `?DSSGetSharedFileName@@YAJPEBGPEAPEAG@Z`
- size: `251`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180007530`

## callees

- `0x180006f78`
- `0x18000be3c`
- `0x18000bf80`
- `0x18000c6d8`
- `0x18000cfcc`
- `0x18000da68`
- `0x18000f120`
- `0x18001abbc`

## string_xrefs

- `0x18000d005`: `Failed to get filename for token: %s. hr=0x%x`

## pseudocode

```c
__int64 __fastcall DSSGetSharedFileName(unsigned __int16 *a1, unsigned __int16 **a2)
{
  int AuthorizedSharingToken; // ebx
  int *v5; // rax
  PVOID v6; // rcx
  __int64 v8; // rbx
  const unsigned __int16 *v9; // rax
  const unsigned __int16 **v10; // r8
  unsigned __int16 *v11; // rax
  __int128 v12; // [rsp+30h] [rbp-18h] BYREF
  PVOID P; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  P = 0;
  if ( !dword_18002B2D0 )
  {
    AuthorizedSharingToken = -1055719422;
LABEL_3:
    v5 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)a1);
    DSLogger::LogError(
      (DSLogger *)v5,
      L"DSSGetSharedFileName",
      596,
      L"Failed to get filename for token: %s. hr=0x%x",
      a1,
      AuthorizedSharingToken);
    v6 = P;
    goto LABEL_4;
  }
  AuthorizedSharingToken = GetAuthorizedSharingToken(a1, 1, (FILETIME **)&v12);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_3;
  v8 = v12;
  if ( !*(_QWORD *)(v12 + 152) )
  {
    AuthorizedSharingToken = -1055719420;
    goto LABEL_3;
  }
  v9 = (const unsigned __int16 *)tlx::replace<unsigned short,&void tlx::_delete_array<unsigned short>(unsigned short *)>(&P);
  AuthorizedSharingToken = DSUtils::AssignStringForRpc(*(DSUtils **)(v8 + 152), v9, v10);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_3;
  v11 = (unsigned __int16 *)P;
  v6 = 0;
  P = 0;
  *a2 = v11;
LABEL_4:
  if ( *((_QWORD *)&v12 + 1) )
  {
    utl::_RefCountBase::_DecStrong(*((utl::_RefCountBase **)&v12 + 1));
    v6 = P;
  }
  if ( v6 )
    Common::GlobalHeap::Free(v6);
  return (unsigned int)AuthorizedSharingToken;
}

```

## disassembly

```asm
0x18000cfcc  mov     rax, rsp
0x18000cfcf  mov     [rax+8], rbx
0x18000cfd3  mov     [rax+10h], rsi
0x18000cfd7  push    rdi
0x18000cfd8  sub     rsp, 40h
0x18000cfdc  cmp     cs:dword_18002B2D0, 0
0x18000cfe3  xorps   xmm0, xmm0
0x18000cfe6  movdqu  xmmword ptr [rax-18h], xmm0
0x18000cfeb  mov     rsi, rdx
0x18000cfee  mov     qword ptr [rax+18h], 0
0x18000cff6  mov     rdi, rcx
0x18000cff9  jnz     short loc_18000D062
0x18000cffb  mov     ebx, 0C1130002h
0x18000d000  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000d005  lea     r9, aFailedToGetFil; "Failed to get filename for token: %s. h"...
0x18000d00c  mov     [rsp+48h+var_20], ebx
0x18000d010  mov     r8d, 254h; unsigned int
0x18000d016  mov     [rsp+48h+var_28], rdi
0x18000d01b  lea     rdx, aDssgetsharedfi; "DSSGetSharedFileName"
0x18000d022  mov     rcx, rax; this
0x18000d025  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000d02a  mov     rcx, [rsp+48h+P]
0x18000d02f  mov     rax, [rsp+48h+var_10]
0x18000d034  test    rax, rax
0x18000d037  jz      short loc_18000D046
0x18000d039  mov     rcx, rax; this
0x18000d03c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18000d041  mov     rcx, [rsp+48h+P]; P
0x18000d046  test    rcx, rcx
0x18000d049  jz      short loc_18000D050
0x18000d04b  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000d050  mov     rsi, [rsp+48h+arg_8]
0x18000d055  mov     eax, ebx
0x18000d057  mov     rbx, [rsp+48h+arg_0]
0x18000d05c  add     rsp, 40h
0x18000d060  pop     rdi
0x18000d061  retn
0x18000d062  lea     r8, [rsp+48h+var_18]
0x18000d067  mov     edx, 1
0x18000d06c  call    GetAuthorizedSharingToken
0x18000d071  mov     ebx, eax
0x18000d073  test    eax, eax
0x18000d075  js      short loc_18000D000
0x18000d077  mov     rbx, [rsp+48h+var_18]
0x18000d07c  cmp     qword ptr [rbx+98h], 0
0x18000d084  jnz     short loc_18000D090
0x18000d086  mov     ebx, 0C1130004h
0x18000d08b  jmp     loc_18000D000
0x18000d090  lea     rcx, [rsp+48h+P]
0x18000d095  call    ??$replace@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@tlx@@YAPEAPEAGAEAV?$auto_array_ptr@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@0@@Z; tlx::replace<ushort,&tlx::_delete_array<ushort>(ushort *)>(tlx::auto_array_ptr<ushort,&tlx::_delete_array<ushort>(ushort *)> &)
0x18000d09a  mov     rcx, [rbx+98h]; this
0x18000d0a1  mov     rdx, rax; unsigned __int16 *
0x18000d0a4  call    ?AssignStringForRpc@DSUtils@@YAJPEBGPEAPEBG@Z; DSUtils::AssignStringForRpc(ushort const *,ushort const * *)
0x18000d0a9  mov     ebx, eax
0x18000d0ab  test    eax, eax
0x18000d0ad  js      loc_18000D000
0x18000d0b3  mov     rax, [rsp+48h+P]
0x18000d0b8  xor     ecx, ecx
0x18000d0ba  mov     [rsp+48h+P], rcx
0x18000d0bf  mov     [rsi], rax
0x18000d0c2  jmp     loc_18000D02F
```
