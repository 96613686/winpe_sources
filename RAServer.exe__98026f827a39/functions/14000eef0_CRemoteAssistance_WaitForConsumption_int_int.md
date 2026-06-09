# CRemoteAssistance::WaitForConsumption(int *,int)

- ea: `0x14000eef0`
- end: `0x14000efaf`
- name: `?WaitForConsumption@CRemoteAssistance@@UEAAJPEAHH@Z`
- size: `191`
- prototype: `__int64 __fastcall(CRemoteAssistance *__hidden this, int *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000eef0`
- `0x140015240`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14000ef6b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14000ef6b`

## string_xrefs

- `0x14000ef44`: `base\diagnosis\ra\dcom\src\remoteassistance.cpp`
- `0x14000ef7b`: `base\diagnosis\ra\dcom\src\remoteassistance.cpp`

## pseudocode

```c
__int64 __fastcall CRemoteAssistance::WaitForConsumption(CRemoteAssistance *this, int *a2, int a3)
{
  __int64 v4; // rdx
  int v5; // ebx
  HRESULT v7; // eax
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  unsigned int v10; // edi
  HANDLE pHandles; // [rsp+40h] [rbp+8h] BYREF
  DWORD dwindex; // [rsp+50h] [rbp+18h] BYREF

  dwindex = 0;
  v4 = 0xFFFFFFFFLL;
  v5 = 1;
  if ( a3 != 1 )
    v4 = 120000;
  pHandles = (HANDLE)*((_QWORD *)this + 11);
  if ( a2 )
  {
    v7 = CoWaitForMultipleHandles(1u, v4, 1u, &pHandles, &dwindex);
    v10 = v7;
    if ( v7 )
    {
      CEventLogger::LogError(
        v9,
        v8,
        L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
        0x2A9u,
        L"CRemoteAssistance::WaitForConsumption",
        v7);
      v5 = 0;
    }
    *a2 = v5;
    return v10;
  }
  else
  {
    CEventLogger::LogError(
      this,
      (const struct _EVENT_DESCRIPTOR *)v4,
      L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
      0x297u,
      L"CRemoteAssistance::WaitForConsumption",
      0x80004003);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x14000eef0  mov     r11, rsp
0x14000eef3  mov     [r11+10h], rbx
0x14000eef7  mov     [r11+20h], rsi
0x14000eefb  push    rdi
0x14000eefc  sub     rsp, 30h
0x14000ef00  mov     rsi, rdx
0x14000ef03  mov     [rsp+38h+dwindex], 0
0x14000ef0b  or      edx, 0FFFFFFFFh
0x14000ef0e  mov     eax, 1D4C0h
0x14000ef13  mov     ebx, 1
0x14000ef18  cmp     r8d, ebx
0x14000ef1b  cmovnz  edx, eax; struct _EVENT_DESCRIPTOR *
0x14000ef1e  mov     rax, [rcx+58h]
0x14000ef22  mov     [r11+8], rax
0x14000ef26  test    rsi, rsi
0x14000ef29  jnz     short loc_14000EF57
0x14000ef2b  lea     rax, aCremoteassista; "CRemoteAssistance::WaitForConsumption"
0x14000ef32  mov     [rsp+38h+var_10], 80004003h; unsigned int
0x14000ef3a  mov     r9d, 297h; unsigned int
0x14000ef40  mov     [r11-18h], rax
0x14000ef44  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\dcom\\src\\remotea"...
0x14000ef4b  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000ef50  mov     eax, 80004003h
0x14000ef55  jmp     short loc_14000EF9F
0x14000ef57  lea     rax, [rsp+38h+dwindex]
0x14000ef5c  mov     r8d, ebx; cHandles
0x14000ef5f  lea     r9, [rsp+38h+pHandles]; pHandles
0x14000ef64  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x14000ef69  mov     ecx, ebx; dwFlags
0x14000ef6b  call    cs:__imp_CoWaitForMultipleHandles
0x14000ef71  mov     edi, eax
0x14000ef73  test    eax, eax
0x14000ef75  jz      short loc_14000EF9B
0x14000ef77  mov     [rsp+38h+var_10], eax; unsigned int
0x14000ef7b  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\dcom\\src\\remotea"...
0x14000ef82  lea     rax, aCremoteassista; "CRemoteAssistance::WaitForConsumption"
0x14000ef89  mov     r9d, 2A9h; unsigned int
0x14000ef8f  mov     [rsp+38h+lpdwindex], rax; unsigned __int16 *
0x14000ef94  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000ef99  xor     ebx, ebx
0x14000ef9b  mov     [rsi], ebx
0x14000ef9d  mov     eax, edi
0x14000ef9f  mov     rbx, [rsp+38h+arg_8]
0x14000efa4  mov     rsi, [rsp+38h+arg_18]
0x14000efa9  add     rsp, 30h
0x14000efad  pop     rdi
0x14000efae  retn
```
