# CNetDiagHelperImpl::GetCacheTime(_FILETIME *)

- ea: `0x18000bf40`
- end: `0x18000bf81`
- name: `?GetCacheTime@CNetDiagHelperImpl@@UEAAJPEAU_FILETIME@@@Z`
- size: `65`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, struct _FILETIME *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000bf40`
- `0x18000fa98`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetCacheTime(CNetDiagHelperImpl *this, struct _FILETIME *a2)
{
  struct _FILETIME *v2; // rbx
  __int64 result; // rax

  v2 = a2;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = 8;
  do
  {
    LOBYTE(v2->dwLowDateTime) = 0;
    v2 = (struct _FILETIME *)((char *)v2 + 1);
    --result;
  }
  while ( result );
  return result;
}

```

## disassembly

```asm
0x18000bf40  mov     [rsp+arg_0], rbx
0x18000bf45  push    rdi
0x18000bf46  sub     rsp, 20h
0x18000bf4a  mov     rbx, rdx
0x18000bf4d  mov     rdi, rcx
0x18000bf50  test    rdx, rdx
0x18000bf53  jnz     short loc_18000BF5A
0x18000bf55  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000bf5a  cmp     dword ptr [rdi+10h], 1
0x18000bf5e  jz      short loc_18000BF65
0x18000bf60  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000bf65  mov     eax, 8
0x18000bf6a  mov     byte ptr [rbx], 0
0x18000bf6d  inc     rbx
0x18000bf70  sub     rax, 1
0x18000bf74  jnz     short loc_18000BF6A
0x18000bf76  mov     rbx, [rsp+28h+arg_0]
0x18000bf7b  add     rsp, 20h
0x18000bf7f  pop     rdi
0x18000bf80  retn
```
