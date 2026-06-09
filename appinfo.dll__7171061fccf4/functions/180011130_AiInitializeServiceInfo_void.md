# AiInitializeServiceInfo(void)

- ea: `0x180011130`
- end: `0x1800111be`
- name: `?AiInitializeServiceInfo@@YAKXZ`
- size: `142`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180028270`

## callees

- `0x180011130`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180011179`
- `ntdll!RtlInitUnicodeString` at `0x180011179`
- `ntdll!RtlCreateServiceSid` at `0x1800111a0`
- `ntdll!RtlCreateServiceSid` at `0x1800111a0`

## string_xrefs

- `0x180011152`: `MSIServer`

## pseudocode

```c
__int64 AiInitializeServiceInfo(void)
{
  __int64 v0; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  PCWSTR SourceString[5]; // [rsp+30h] [rbp-28h]
  ULONG ServiceSidLength; // [rsp+60h] [rbp+8h] BYREF

  ServiceSidLength = 0;
  SourceString[0] = L"Rpcss";
  v0 = 0;
  SourceString[1] = L"MSIServer";
  SourceString[2] = L"AxInstSv";
  DestinationString = 0;
  do
  {
    RtlInitUnicodeString(&DestinationString, SourceString[v0]);
    ServiceSidLength = 72;
    if ( RtlCreateServiceSid(&DestinationString, &g_pServiceInfo + 9 * v0, &ServiceSidLength) < 0 )
      break;
    v0 = (unsigned int)(v0 + 1);
  }
  while ( (unsigned int)v0 < 3 );
  return 0;
}

```

## disassembly

```asm
0x180011130  mov     r11, rsp
0x180011133  mov     [r11+10h], rbx
0x180011137  push    rdi
0x180011138  sub     rsp, 50h
0x18001113c  lea     rax, aRpcss; "Rpcss"
0x180011143  mov     [rsp+58h+ServiceSidLength], 0
0x18001114b  mov     [r11-28h], rax
0x18001114f  xorps   xmm0, xmm0
0x180011152  lea     rax, aMsiserver; "MSIServer"
0x180011159  xor     edi, edi
0x18001115b  mov     [r11-20h], rax
0x18001115f  lea     rax, aAxinstsv; "AxInstSv"
0x180011166  mov     [r11-18h], rax
0x18001116a  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x18001116f  mov     rdx, [rsp+rdi*8+58h+SourceString]; SourceString
0x180011174  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x180011179  call    cs:__imp_RtlInitUnicodeString
0x18001117f  lea     rax, [rdi+rdi*8]
0x180011183  mov     [rsp+58h+ServiceSidLength], 48h ; 'H'
0x18001118b  lea     rcx, ?g_pServiceInfo@@3PAU_SERVICE_INFO@@A; _SERVICE_INFO near * g_pServiceInfo
0x180011192  lea     rdx, [rcx+rax*8]; ServiceSid
0x180011196  lea     rcx, [rsp+58h+DestinationString]; ServiceName
0x18001119b  lea     r8, [rsp+58h+ServiceSidLength]; ServiceSidLength
0x1800111a0  call    cs:__imp_RtlCreateServiceSid
0x1800111a6  test    eax, eax
0x1800111a8  js      short loc_1800111B1
0x1800111aa  inc     edi
0x1800111ac  cmp     edi, 3
0x1800111af  jb      short loc_18001116F
0x1800111b1  mov     rbx, [rsp+58h+arg_8]
0x1800111b6  xor     eax, eax
0x1800111b8  add     rsp, 50h
0x1800111bc  pop     rdi
0x1800111bd  retn
```
