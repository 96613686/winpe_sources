# HttpResponse::StatusCode(void)

- ea: `0x180048cc0`
- end: `0x180048d2e`
- name: `?StatusCode@HttpResponse@@QEBAKXZ`
- size: `110`
- prototype: `unsigned int __fastcall(HttpResponse *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800374d4`
- `0x180048138`

## callees

- `0x180030a68`
- `0x180048cc0`

## import_xrefs

- `WINHTTP!WinHttpQueryHeaders` at `0x180048cff`
- `WINHTTP!WinHttpQueryHeaders` at `0x180048cff`

## string_xrefs

- `0x180048d1c`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
__int64 __fastcall HttpResponse::StatusCode(HttpResponse *this)
{
  void *v1; // rax
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v5; // [rsp+40h] [rbp+8h] BYREF
  DWORD v6; // [rsp+48h] [rbp+10h] BYREF

  v1 = (void *)*((_QWORD *)this + 6);
  v5 = 0;
  if ( !v1 )
    return *((unsigned int *)this + 8);
  v6 = 4;
  if ( !WinHttpQueryHeaders(v1, 0x20000013u, 0, &v5, &v6, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x382,
      (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v2);
  return v5;
}

```

## disassembly

```asm
0x180048cc0  mov     r11, rsp
0x180048cc3  sub     rsp, 38h
0x180048cc7  mov     rax, [rcx+30h]
0x180048ccb  mov     [rsp+38h+arg_0], 0
0x180048cd3  test    rax, rax
0x180048cd6  jz      short loc_180048D0F
0x180048cd8  lea     rcx, [r11+10h]
0x180048cdc  mov     qword ptr [r11-10h], 0
0x180048ce4  mov     [r11-18h], rcx
0x180048ce8  lea     r9, [r11+8]; lpBuffer
0x180048cec  mov     rcx, rax; hRequest
0x180048cef  mov     [rsp+38h+arg_8], 4
0x180048cf7  xor     r8d, r8d; pwszName
0x180048cfa  mov     edx, 20000013h; dwInfoLevel
0x180048cff  call    cs:__imp_WinHttpQueryHeaders
0x180048d05  test    eax, eax
0x180048d07  jz      short loc_180048D17
0x180048d09  mov     eax, [rsp+38h+arg_0]
0x180048d0d  jmp     short loc_180048D12
0x180048d0f  mov     eax, [rcx+20h]
0x180048d12  add     rsp, 38h
0x180048d16  retn
0x180048d17  mov     rcx, [rsp+38h]; this
0x180048d1c  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x180048d23  mov     edx, 382h; void *
0x180048d28  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
