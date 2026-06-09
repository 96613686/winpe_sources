# CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *,uint,uint)

- ea: `0x140015548`
- end: `0x1400155f7`
- name: `?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGII@Z`
- size: `175`
- prototype: `__int64 __fastcall(CEventLogger *this, const struct _EVENT_DESCRIPTOR *, unsigned __int16 *, int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140011fc0`
- `0x140013250`

## callees

- `0x140011394`
- `0x140015548`
- `0x140015aa0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x1400155cf`
- `ADVAPI32!EventWrite` at `0x1400155cf`

## pseudocode

```c
__int64 __fastcall CEventLogger::LogEvent(
        CEventLogger *this,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned __int16 *a3,
        int a4,
        unsigned int a5)
{
  ULONGLONG v5; // r11
  unsigned __int64 v7; // [rsp+20h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-38h] BYREF
  int *v9; // [rsp+38h] [rbp-28h]
  __int64 v10; // [rsp+40h] [rbp-20h]
  unsigned int *v11; // [rsp+48h] [rbp-18h]
  __int64 v12; // [rsp+50h] [rbp-10h]
  int v13; // [rsp+88h] [rbp+28h] BYREF

  v13 = a4;
  v7 = 0;
  if ( (int)StringCbLengthW(a3, 0xFFFFFFFE, &v7) < 0 )
    return 2147500037LL;
  UserData.Ptr = v5;
  UserData.Size = v7 + 2;
  UserData.Reserved = 0;
  v9 = &v13;
  v11 = &a5;
  v10 = 4;
  v12 = 4;
  return EventWrite(g_Logger, &Switch_On, 3u, &UserData) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x140015548  mov     [rsp-8+arg_18], r9d
0x14001554d  push    rbp
0x14001554e  mov     rbp, rsp
0x140015551  sub     rsp, 60h
0x140015555  mov     rax, cs:__security_cookie
0x14001555c  xor     rax, rsp
0x14001555f  mov     [rbp+var_8], rax
0x140015563  mov     r11, r8
0x140015566  mov     [rbp+var_40], 0
0x14001556e  mov     rcx, r11; unsigned __int16 *
0x140015571  lea     r8, [rbp+var_40]; unsigned __int64 *
0x140015575  mov     edx, 0FFFFFFFEh; unsigned __int64
0x14001557a  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001557f  test    eax, eax
0x140015581  js      short loc_1400155E0
0x140015583  mov     eax, dword ptr [rbp+var_40]
0x140015586  lea     r9, [rbp+UserData]; UserData
0x14001558a  mov     rcx, cs:?g_Logger@@3VCEventLogger@@A; RegHandle
0x140015591  lea     rdx, Switch_On; EventDescriptor
0x140015598  add     eax, 2
0x14001559b  mov     [rbp+UserData.Ptr], r11
0x14001559f  mov     [rbp+UserData.Size], eax
0x1400155a2  mov     r8d, 3; UserDataCount
0x1400155a8  lea     rax, [rbp+arg_18]
0x1400155ac  mov     dword ptr [rbp+UserData.0Ch], 0
0x1400155b3  mov     [rbp+var_28], rax
0x1400155b7  lea     rax, [rbp+arg_20]
0x1400155bb  mov     [rbp+var_18], rax
0x1400155bf  mov     [rbp+var_20], 4
0x1400155c7  mov     [rbp+var_10], 4
0x1400155cf  call    cs:__imp_EventWrite
0x1400155d5  neg     eax
0x1400155d7  sbb     eax, eax
0x1400155d9  and     eax, 80004005h
0x1400155de  jmp     short loc_1400155E5
0x1400155e0  mov     eax, 80004005h
0x1400155e5  mov     rcx, [rbp+var_8]
0x1400155e9  xor     rcx, rsp; StackCookie
0x1400155ec  call    __security_check_cookie
0x1400155f1  add     rsp, 60h
0x1400155f5  pop     rbp
0x1400155f6  retn
```
