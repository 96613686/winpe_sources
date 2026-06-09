# WindowsMidiServicesInternal::StringToGuid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x140026070`
- end: `0x1400260dd`
- name: `?StringToGuid@WindowsMidiServicesInternal@@YA?AU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002455c`
- `0x140043720`

## callees

- `0x1400054c0`
- `0x140007c20`
- `0x140026070`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1400260ab`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1400260ab`

## pseudocode

```c
CLSID *__fastcall WindowsMidiServicesInternal::StringToGuid(CLSID *a1, __int64 a2)
{
  bool v2; // cc
  char *v5; // rcx
  CLSID pclsid; // [rsp+28h] [rbp-20h] BYREF

  v2 = *(_QWORD *)(a2 + 24) <= 7u;
  pclsid = 0;
  if ( v2 )
    v5 = (char *)a2;
  else
    v5 = *(char **)a2;
  CLSIDFromString((LPCOLESTR)v5, &pclsid);
  *a1 = pclsid;
  std::wstring::~wstring((char **)a2);
  return a1;
}

```

## disassembly

```asm
0x140026070  mov     [rsp+arg_0], rbx
0x140026075  push    rdi
0x140026076  sub     rsp, 40h
0x14002607a  mov     rax, cs:__security_cookie
0x140026081  xor     rax, rsp
0x140026084  mov     [rsp+48h+var_10], rax
0x140026089  cmp     qword ptr [rdx+18h], 7
0x14002608e  xorps   xmm0, xmm0
0x140026091  movups  xmmword ptr [rsp+48h+pclsid.Data1], xmm0
0x140026096  mov     rbx, rdx
0x140026099  mov     rdi, rcx
0x14002609c  jbe     short loc_1400260A3
0x14002609e  mov     rcx, [rdx]
0x1400260a1  jmp     short loc_1400260A6
0x1400260a3  mov     rcx, rbx; lpsz
0x1400260a6  lea     rdx, [rsp+48h+pclsid]; pclsid
0x1400260ab  call    cs:__imp_CLSIDFromString
0x1400260b1  movups  xmm0, xmmword ptr [rsp+48h+pclsid.Data1]
0x1400260b6  mov     rcx, rbx; void *
0x1400260b9  movdqu  xmmword ptr [rdi], xmm0
0x1400260bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400260c2  mov     rax, rdi
0x1400260c5  mov     rcx, [rsp+48h+var_10]
0x1400260ca  xor     rcx, rsp; StackCookie
0x1400260cd  call    __security_check_cookie
0x1400260d2  mov     rbx, [rsp+48h+arg_0]
0x1400260d7  add     rsp, 40h
0x1400260db  pop     rdi
0x1400260dc  retn
```
