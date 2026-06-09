# FwSetSerializeVersion(ushort const *,ushort,HKEY__ *)

- ea: `0x180039818`
- end: `0x1800398a7`
- name: `?FwSetSerializeVersion@@YAJPEBGGPEAUHKEY__@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16, HKEY)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037db0`
- `0x180037fc0`
- `0x180038b20`
- `0x180038fa0`
- `0x180039218`

## callees

- `0x18000cff0`
- `0x18001e9ac`
- `0x18001f650`
- `0x180039818`

## import_xrefs

- `fwbase!FwRegSetString` at `0x180039886`
- `fwbase!FwRegSetString` at `0x180039886`

## pseudocode

```c
__int64 __fastcall FwSetSerializeVersion(const unsigned __int16 *a1, unsigned __int16 a2, HKEY a3)
{
  int v6; // [rsp+30h] [rbp-38h]
  int v7; // [rsp+38h] [rbp-30h]
  wchar_t pszDest[12]; // [rsp+40h] [rbp-28h] BYREF

  v7 = (unsigned __int8)a2;
  v6 = HIBYTE(a2);
  if ( (int)StringCchPrintfExW(pszDest, 9u, 0, 0, 0x800u, L"%d.%d", v6, v7) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return FwRegSetString(a3, 0, a1, pszDest);
}

```

## disassembly

```asm
0x180039818  mov     [rsp+arg_18], rbx
0x18003981d  push    rdi
0x18003981e  sub     rsp, 60h
0x180039822  mov     rax, cs:__security_cookie
0x180039829  xor     rax, rsp
0x18003982c  mov     [rsp+68h+var_10], rax
0x180039831  mov     rbx, rcx
0x180039834  xor     r9d, r9d; unsigned __int64 *
0x180039837  movzx   ecx, dx
0x18003983a  mov     rdi, r8
0x18003983d  movzx   eax, cl
0x180039840  xor     r8d, r8d; unsigned __int16 **
0x180039843  mov     [rsp+68h+var_30], eax
0x180039847  lea     rax, aDD; "%d.%d"
0x18003984e  shr     ecx, 8
0x180039851  lea     edx, [r9+9]; unsigned __int64
0x180039855  mov     [rsp+68h+var_38], ecx
0x180039859  lea     rcx, [rsp+68h+pszDest]; pszDest
0x18003985e  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x180039863  mov     [rsp+68h+var_48], 800h; unsigned int
0x18003986b  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180039870  test    eax, eax
0x180039872  jns     short loc_180039879
0x180039874  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180039879  lea     r9, [rsp+68h+pszDest]
0x18003987e  mov     r8, rbx
0x180039881  xor     edx, edx
0x180039883  mov     rcx, rdi
0x180039886  call    cs:__imp_FwRegSetString
0x18003988c  mov     rcx, [rsp+68h+var_10]
0x180039891  xor     rcx, rsp; StackCookie
0x180039894  call    __security_check_cookie
0x180039899  mov     rbx, [rsp+68h+arg_18]
0x1800398a1  add     rsp, 60h
0x1800398a5  pop     rdi
0x1800398a6  retn
```
