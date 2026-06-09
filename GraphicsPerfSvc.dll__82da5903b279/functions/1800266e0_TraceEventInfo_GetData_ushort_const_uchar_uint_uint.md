# TraceEventInfo::GetData(ushort const *,uchar *,uint,uint)

- ea: `0x1800266e0`
- end: `0x180026762`
- name: `?GetData@TraceEventInfo@@QEAAXPEBGPEAEII@Z`
- size: `130`
- prototype: `void __fastcall(TraceEventInfo *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019ee0`
- `0x180026768`

## callees

- `0x180003ab0`
- `0x18001c068`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18002672c`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18002672c`

## string_xrefs

- `0x18002673b`: `onecore\windows\directx\dxg\common\etwtracesession\traceeventinfo.cpp`

## pseudocode

```c
void __fastcall TraceEventInfo::GetData(
        TraceEventInfo *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        ULONG a4,
        ULONG a5)
{
  struct _EVENT_RECORD *v5; // rcx
  TDHSTATUS Property; // eax
  unsigned int v7; // [rsp+20h] [rbp-48h]
  PROPERTY_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = (struct _EVENT_RECORD *)*((_QWORD *)this + 2);
  v8.ArrayIndex = a5;
  v8.Reserved = 0;
  v8.PropertyName = (ULONGLONG)a2;
  Property = TdhGetProperty(v5, 0, 0, 1u, &v8, a4, a3);
  if ( Property )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\windows\\directx\\dxg\\common\\etwtracesession\\traceeventinfo.cpp",
      (const char *)Property,
      v7);
}

```

## disassembly

```asm
0x1800266e0  mov     r11, rsp
0x1800266e3  sub     rsp, 68h
0x1800266e7  mov     rax, cs:__security_cookie
0x1800266ee  xor     rax, rsp
0x1800266f1  mov     [rsp+68h+var_18], rax
0x1800266f6  mov     eax, [rsp+68h+arg_20]
0x1800266fd  mov     rcx, [rcx+10h]; pEvent
0x180026701  mov     [r11-38h], r8
0x180026705  xor     r8d, r8d; pTdhContext
0x180026708  mov     [rsp+68h+var_20], eax
0x18002670c  lea     rax, [r11-28h]
0x180026710  mov     [r11-40h], r9d
0x180026714  mov     r9d, 1; PropertyDataCount
0x18002671a  mov     [rsp+68h+var_1C], 0
0x180026722  mov     [r11-28h], rdx
0x180026726  xor     edx, edx; TdhContextCount
0x180026728  mov     [r11-48h], rax
0x18002672c  call    cs:__imp_TdhGetProperty
0x180026732  test    eax, eax
0x180026734  jz      short loc_180026750
0x180026736  mov     rcx, [rsp+68h]; this
0x18002673b  lea     r8, aOnecoreWindows_0; "onecore\\windows\\directx\\dxg\\common"...
0x180026742  mov     r9d, eax; char *
0x180026745  mov     edx, 45h ; 'E'; void *
0x18002674a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180026750  mov     rcx, [rsp+68h+var_18]
0x180026755  xor     rcx, rsp; StackCookie
0x180026758  call    __security_check_cookie
0x18002675d  add     rsp, 68h
0x180026761  retn
```
