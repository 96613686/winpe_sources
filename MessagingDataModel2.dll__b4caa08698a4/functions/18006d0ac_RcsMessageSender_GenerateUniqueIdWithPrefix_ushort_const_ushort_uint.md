# RcsMessageSender::_GenerateUniqueIdWithPrefix(ushort const *,ushort *,uint)

- ea: `0x18006d0ac`
- end: `0x18006d169`
- name: `?_GenerateUniqueIdWithPrefix@RcsMessageSender@@AEAAJPEBGPEAGI@Z`
- size: `189`
- prototype: `int(RcsMessageSender *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18006d374`

## callees

- `0x180015050`
- `0x18006ba44`
- `0x18006d0ac`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006d10d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006d10d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006d0db`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006d0db`

## string_xrefs

- `0x18006d11d`: `temprcs`

## pseudocode

```c
__int64 __fastcall RcsMessageSender::_GenerateUniqueIdWithPrefix(
        RcsMessageSender *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  HRESULT v4; // ebx
  GUID pguid; // [rsp+30h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-68h] BYREF

  pguid = 0;
  v4 = CoCreateGuid(&pguid);
  if ( v4 >= 0 )
  {
    StringFromGUID2(&pguid, sz, 39);
    v4 = StringCchPrintfW(a3, 0x2Fu, L"%s%s", L"temprcs", sz);
    if ( v4 >= 0 )
      return 0;
  }
  Log_HREvent_47(v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006d0ac  mov     [rsp+arg_0], rbx
0x18006d0b1  push    rdi
0x18006d0b2  sub     rsp, 0A0h
0x18006d0b9  mov     rax, cs:__security_cookie
0x18006d0c0  xor     rax, rsp
0x18006d0c3  mov     [rsp+0A8h+var_18], rax
0x18006d0cb  xorps   xmm0, xmm0
0x18006d0ce  lea     rcx, [rsp+0A8h+pguid]; pguid
0x18006d0d3  movups  xmmword ptr [rsp+0A8h+pguid.Data1], xmm0
0x18006d0d8  mov     rdi, r8
0x18006d0db  call    cs:__imp_CoCreateGuid
0x18006d0e1  mov     ebx, eax
0x18006d0e3  test    eax, eax
0x18006d0e5  jns     short loc_18006D0FD
0x18006d0e7  mov     r9d, 439h
0x18006d0ed  mov     edx, 1
0x18006d0f2  mov     ecx, ebx; int
0x18006d0f4  call    Log_HREvent_47
0x18006d0f9  mov     eax, ebx
0x18006d0fb  jmp     short loc_18006D148
0x18006d0fd  mov     r8d, 27h ; '''; cchMax
0x18006d103  lea     rdx, [rsp+0A8h+sz]; lpsz
0x18006d108  lea     rcx, [rsp+0A8h+pguid]; rguid
0x18006d10d  call    cs:__imp_StringFromGUID2
0x18006d113  lea     rax, [rsp+0A8h+sz]
0x18006d118  mov     edx, 2Fh ; '/'; unsigned __int64
0x18006d11d  lea     r9, ?c_RcsTempRemoteIdPrefix@@3QBGB; "temprcs"
0x18006d124  mov     [rsp+0A8h+var_88], rax
0x18006d129  lea     r8, aSS; "%s%s"
0x18006d130  mov     rcx, rdi; unsigned __int16 *
0x18006d133  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006d138  mov     ebx, eax
0x18006d13a  test    eax, eax
0x18006d13c  jns     short loc_18006D146
0x18006d13e  mov     r9d, 43Eh
0x18006d144  jmp     short loc_18006D0ED
0x18006d146  xor     eax, eax
0x18006d148  mov     rcx, [rsp+0A8h+var_18]
0x18006d150  xor     rcx, rsp; StackCookie
0x18006d153  call    __security_check_cookie
0x18006d158  mov     rbx, [rsp+0A8h+arg_0]
0x18006d160  add     rsp, 0A0h
0x18006d167  pop     rdi
0x18006d168  retn
```
