# CTypelibCache::UpdateMappedCLSID(_GUID *)

- ea: `0x180060b20`
- end: `0x180060bcb`
- name: `?UpdateMappedCLSID@CTypelibCache@@QEAAJPEAU_GUID@@@Z`
- size: `171`
- prototype: `int(CTypelibCache *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003929c`

## callees

- `0x180006ed4`
- `0x180023dd0`
- `0x180060b20`

## import_xrefs

- `ole32!CLSIDFromProgID` at `0x180060b77`
- `ole32!CLSIDFromProgID` at `0x180060b77`
- `KERNEL32!LeaveCriticalSection` at `0x180060bab`
- `KERNEL32!LeaveCriticalSection` at `0x180060bab`
- `KERNEL32!EnterCriticalSection` at `0x180060b50`
- `KERNEL32!EnterCriticalSection` at `0x180060b50`

## pseudocode

```c
__int64 __fastcall CTypelibCache::UpdateMappedCLSID(CTypelibCache *this, struct _GUID *a2)
{
  unsigned int v3; // edi
  struct CLinkElem *Elem; // rax
  __int64 v5; // rax
  CLSID clsid; // [rsp+20h] [rbp-28h] BYREF

  clsid = 0;
  v3 = 1;
  EnterCriticalSection(&stru_18007D278);
  Elem = CHashTable::FindElem((CHashTable *)&qword_18007D178, a2, 16);
  if ( Elem && CLSIDFromProgID(*((LPCOLESTR *)Elem + 6), &clsid) >= 0 )
  {
    v5 = *(_QWORD *)&clsid.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&clsid.Data1 == *(_QWORD *)&a2->Data1 )
      v5 = *(_QWORD *)clsid.Data4 - *(_QWORD *)a2->Data4;
    if ( v5 )
    {
      v3 = 0;
      *a2 = clsid;
    }
  }
  LeaveCriticalSection(&stru_18007D278);
  return v3;
}

```

## disassembly

```asm
0x180060b20  mov     [rsp+arg_0], rbx
0x180060b25  push    rdi
0x180060b26  sub     rsp, 40h
0x180060b2a  mov     rax, cs:__security_cookie
0x180060b31  xor     rax, rsp
0x180060b34  mov     [rsp+48h+var_18], rax
0x180060b39  xorps   xmm0, xmm0
0x180060b3c  lea     rcx, stru_18007D278; lpCriticalSection
0x180060b43  movups  xmmword ptr [rsp+48h+clsid.Data1], xmm0
0x180060b48  mov     rbx, rdx
0x180060b4b  mov     edi, 1
0x180060b50  call    cs:__imp_EnterCriticalSection
0x180060b56  lea     r8d, [rdi+0Fh]; int
0x180060b5a  mov     rdx, rbx; void *
0x180060b5d  lea     rcx, qword_18007D178; this
0x180060b64  call    ?FindElem@CHashTable@@QEAAPEAUCLinkElem@@PEBXH@Z; CHashTable::FindElem(void const *,int)
0x180060b69  test    rax, rax
0x180060b6c  jz      short loc_180060BA4
0x180060b6e  mov     rcx, [rax+30h]; lpszProgID
0x180060b72  lea     rdx, [rsp+48h+clsid]; lpclsid
0x180060b77  call    cs:__imp_CLSIDFromProgID
0x180060b7d  test    eax, eax
0x180060b7f  js      short loc_180060BA4
0x180060b81  mov     rax, qword ptr [rsp+48h+clsid.Data1]
0x180060b86  sub     rax, [rbx]
0x180060b89  jnz     short loc_180060B94
0x180060b8b  mov     rax, qword ptr [rsp+48h+clsid.Data4]
0x180060b90  sub     rax, [rbx+8]
0x180060b94  test    rax, rax
0x180060b97  jz      short loc_180060BA4
0x180060b99  movups  xmm0, xmmword ptr [rsp+48h+clsid.Data1]
0x180060b9e  xor     edi, edi
0x180060ba0  movdqu  xmmword ptr [rbx], xmm0
0x180060ba4  lea     rcx, stru_18007D278; lpCriticalSection
0x180060bab  call    cs:__imp_LeaveCriticalSection
0x180060bb1  mov     eax, edi
0x180060bb3  mov     rcx, [rsp+48h+var_18]
0x180060bb8  xor     rcx, rsp; StackCookie
0x180060bbb  call    __security_check_cookie
0x180060bc0  mov     rbx, [rsp+48h+arg_0]
0x180060bc5  add     rsp, 40h
0x180060bc9  pop     rdi
0x180060bca  retn
```
