# SocketBrokerContext::Impersonate(void)

- ea: `0x1800128a8`
- end: `0x1800128f2`
- name: `?Impersonate@SocketBrokerContext@@QEAAKXZ`
- size: `74`
- prototype: `__int64 __fastcall(SocketBrokerContext *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012490`
- `0x1800272e8`

## callees

- `0x18000a0a0`
- `0x1800128a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128d0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800128c6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800128c6`

## string_xrefs

- `0x1800128e4`: `Impersonate: SetThreadToken failed`

## pseudocode

```c
__int64 __fastcall SocketBrokerContext::Impersonate(SocketBrokerContext *this)
{
  void *v1; // rdx
  DWORD v2; // ebx
  DWORD LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx

  v1 = (void *)*((_QWORD *)this + 7);
  if ( v1 )
  {
    v2 = 0;
    if ( !SetThreadToken(0, v1) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v6, v5, L"Impersonate: SetThreadToken failed", LastError);
    }
  }
  else
  {
    return 87;
  }
  return v2;
}

```

## disassembly

```asm
0x1800128a8  push    rbx
0x1800128aa  sub     rsp, 20h
0x1800128ae  mov     rdx, [rcx+38h]; Token
0x1800128b2  test    rdx, rdx
0x1800128b5  jnz     short loc_1800128C2
0x1800128b7  lea     ebx, [rdx+57h]
0x1800128ba  mov     eax, ebx
0x1800128bc  add     rsp, 20h
0x1800128c0  pop     rbx
0x1800128c1  retn
0x1800128c2  xor     ecx, ecx; Thread
0x1800128c4  xor     ebx, ebx
0x1800128c6  call    cs:__imp_SetThreadToken
0x1800128cc  test    eax, eax
0x1800128ce  jnz     short loc_1800128BA
0x1800128d0  call    cs:__imp_GetLastError
0x1800128d6  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800128dd  mov     ebx, eax
0x1800128df  jz      short loc_1800128BA
0x1800128e1  mov     r9d, eax
0x1800128e4  lea     r8, aImpersonateSet; "Impersonate: SetThreadToken failed"
0x1800128eb  call    McTemplateU0zq_EventWriteTransfer
0x1800128f0  jmp     short loc_1800128BA
```
