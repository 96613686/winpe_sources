# AuthHostWebInstance::GetAuthHostPageStateString(AuthHostWebInstance::AuthHostPageState)

- ea: `0x1400091b8`
- end: `0x14000920d`
- name: `?GetAuthHostPageStateString@AuthHostWebInstance@@AEAAPEBGW4AuthHostPageState@1@@Z`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140009b84`
- `0x14000b840`

## callees

- `0x1400091b8`

## string_xrefs

- `0x1400091dd`: `Complete`

## pseudocode

```c
const wchar_t *__fastcall AuthHostWebInstance::GetAuthHostPageStateString(__int64 a1, int a2)
{
  int v2; // edx
  int v3; // edx
  int v4; // edx
  int v5; // edx

  if ( !a2 )
    return L"Null";
  v2 = a2 - 1;
  if ( !v2 )
    return L"Start";
  v3 = v2 - 1;
  if ( !v3 )
    return L"Web";
  v4 = v3 - 1;
  if ( !v4 )
    return L"PendingError";
  v5 = v4 - 1;
  if ( !v5 )
    return L"Error";
  if ( v5 == 1 )
    return L"Complete";
  return (const wchar_t *)L"Unexpected";
}

```

## disassembly

```asm
0x1400091b8  test    edx, edx
0x1400091ba  jz      short loc_140009205
0x1400091bc  sub     edx, 1
0x1400091bf  jz      short loc_1400091FD
0x1400091c1  sub     edx, 1
0x1400091c4  jz      short loc_1400091F5
0x1400091c6  sub     edx, 1
0x1400091c9  jz      short loc_1400091ED
0x1400091cb  sub     edx, 1
0x1400091ce  jz      short loc_1400091E5
0x1400091d0  cmp     edx, 1
0x1400091d3  jz      short loc_1400091DD
0x1400091d5  lea     rax, aUnexpected; "Unexpected"
0x1400091dc  retn
0x1400091dd  lea     rax, aComplete; "Complete"
0x1400091e4  retn
0x1400091e5  lea     rax, aError; "Error"
0x1400091ec  retn
0x1400091ed  lea     rax, aPendingerror; "PendingError"
0x1400091f4  retn
0x1400091f5  lea     rax, aWeb; "Web"
0x1400091fc  retn
0x1400091fd  lea     rax, aStart; "Start"
0x140009204  retn
0x140009205  lea     rax, aNull; "Null"
0x14000920c  retn
```
