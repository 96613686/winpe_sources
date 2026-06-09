# CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)

- ea: `0x140015400`
- end: `0x1400154a8`
- name: `?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z`
- size: `168`
- prototype: `__int64 __fastcall(CEventLogger *this, const struct _EVENT_DESCRIPTOR *, int, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f90c`
- `0x140010178`
- `0x140010868`
- `0x140011fc0`
- `0x140013250`

## callees

- `0x140011394`
- `0x140015400`
- `0x140015aa0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x14001547b`
- `ADVAPI32!EventWrite` at `0x14001547b`

## pseudocode

```c
__int64 __fastcall CEventLogger::LogEvent(
        CEventLogger *this,
        const struct _EVENT_DESCRIPTOR *a2,
        int a3,
        unsigned __int16 *a4)
{
  __int64 v5; // r11
  unsigned __int64 v7; // [rsp+20h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-28h] BYREF
  __int64 v9; // [rsp+38h] [rbp-18h]
  int v10; // [rsp+40h] [rbp-10h]
  int v11; // [rsp+44h] [rbp-Ch]
  int v12; // [rsp+70h] [rbp+20h] BYREF

  v12 = a3;
  v7 = 0;
  if ( (int)StringCbLengthW(a4, 0xFFFFFFFE, &v7) < 0 )
    return 2147500037LL;
  UserData.Ptr = (ULONGLONG)&v12;
  *(_QWORD *)&UserData.Size = 4;
  v10 = v7 + 2;
  v9 = v5;
  v11 = 0;
  return EventWrite(g_Logger, a2, 2u, &UserData) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x140015400  mov     [rsp-8+arg_0], rbx
0x140015405  mov     [rsp-8+arg_10], r8d
0x14001540a  push    rbp
0x14001540b  mov     rbp, rsp
0x14001540e  sub     rsp, 50h
0x140015412  mov     rax, cs:__security_cookie
0x140015419  xor     rax, rsp
0x14001541c  mov     [rbp+var_8], rax
0x140015420  mov     rbx, rdx
0x140015423  mov     [rbp+var_30], 0
0x14001542b  mov     edx, 0FFFFFFFEh; unsigned __int64
0x140015430  lea     r8, [rbp+var_30]; unsigned __int64 *
0x140015434  mov     rcx, r9; unsigned __int16 *
0x140015437  mov     r11, r9
0x14001543a  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001543f  test    eax, eax
0x140015441  js      short loc_14001548C
0x140015443  mov     rcx, cs:?g_Logger@@3VCEventLogger@@A; RegHandle
0x14001544a  lea     rax, [rbp+arg_10]
0x14001544e  mov     [rbp+UserData.Ptr], rax
0x140015452  lea     r9, [rbp+UserData]; UserData
0x140015456  mov     eax, dword ptr [rbp+var_30]
0x140015459  mov     r8d, 2; UserDataCount
0x14001545f  add     eax, 2
0x140015462  mov     qword ptr [rbp+UserData.Size], 4
0x14001546a  mov     rdx, rbx; EventDescriptor
0x14001546d  mov     [rbp+var_10], eax
0x140015470  mov     [rbp+var_18], r11
0x140015474  mov     [rbp+var_C], 0
0x14001547b  call    cs:__imp_EventWrite
0x140015481  neg     eax
0x140015483  sbb     eax, eax
0x140015485  and     eax, 80004005h
0x14001548a  jmp     short loc_140015491
0x14001548c  mov     eax, 80004005h
0x140015491  mov     rcx, [rbp+var_8]
0x140015495  xor     rcx, rsp; StackCookie
0x140015498  call    __security_check_cookie
0x14001549d  mov     rbx, [rsp+50h+arg_0]
0x1400154a2  add     rsp, 50h
0x1400154a6  pop     rbp
0x1400154a7  retn
```
