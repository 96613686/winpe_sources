# CommonUtil::ServiceControlToString(ulong)

- ea: `0x140016b34`
- end: `0x140016bc8`
- name: `?ServiceControlToString@CommonUtil@@YAPEB_WK@Z`
- size: `148`
- prototype: `const wchar_t *__fastcall(CommonUtil *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140015e60`

## callees

- `0x140016b34`

## string_xrefs

- `0x140016bc0`: `SERVICE_CONTROL_STOP`
- `0x140016bb8`: `SERVICE_CONTROL_PAUSE`
- `0x140016bb0`: `SERVICE_CONTROL_CONTINUE`
- `0x140016ba8`: `SERVICE_CONTROL_INTERROGATE`
- `0x140016ba0`: `SERVICE_CONTROL_PARAMCHANGE`
- `0x140016b98`: `SERVICE_CONTROL_NETBINDADD`
- `0x140016b90`: `SERVICE_CONTROL_NETBINDREMOVE`
- `0x140016b88`: `SERVICE_CONTROL_NETBINDENABLE`
- `0x140016b80`: `SERVICE_CONTROL_NETBINDDISABLE`
- `0x140016b6a`: `SERVICE_USER_DEFINED_CONTROL`
- `0x140016b74`: `SERVICE_CONTROL_UNKNOWN`

## pseudocode

```c
const wchar_t *__fastcall CommonUtil::ServiceControlToString(CommonUtil *this)
{
  const wchar_t *result; // rax

  switch ( (_DWORD)this )
  {
    case 1:
      return L"SERVICE_CONTROL_STOP";
    case 2:
      return L"SERVICE_CONTROL_PAUSE";
    case 3:
      return L"SERVICE_CONTROL_CONTINUE";
    case 4:
      return L"SERVICE_CONTROL_INTERROGATE";
    case 6:
      return L"SERVICE_CONTROL_PARAMCHANGE";
    case 7:
      return L"SERVICE_CONTROL_NETBINDADD";
    case 8:
      return L"SERVICE_CONTROL_NETBINDREMOVE";
    case 9:
      return L"SERVICE_CONTROL_NETBINDENABLE";
    case 0xA:
      return L"SERVICE_CONTROL_NETBINDDISABLE";
  }
  result = L"SERVICE_CONTROL_UNKNOWN";
  if ( (unsigned int)((_DWORD)this - 128) <= 0x7F )
    return L"SERVICE_USER_DEFINED_CONTROL";
  return result;
}

```

## disassembly

```asm
0x140016b34  mov     eax, ecx
0x140016b36  sub     eax, 1
0x140016b39  jz      loc_140016BC0
0x140016b3f  sub     eax, 1
0x140016b42  jz      short loc_140016BB8
0x140016b44  sub     eax, 1
0x140016b47  jz      short loc_140016BB0
0x140016b49  sub     eax, 1
0x140016b4c  jz      short loc_140016BA8
0x140016b4e  sub     eax, 2
0x140016b51  jz      short loc_140016BA0
0x140016b53  sub     eax, 1
0x140016b56  jz      short loc_140016B98
0x140016b58  sub     eax, 1
0x140016b5b  jz      short loc_140016B90
0x140016b5d  sub     eax, 1
0x140016b60  jz      short loc_140016B88
0x140016b62  cmp     eax, 1
0x140016b65  jz      short loc_140016B80
0x140016b67  add     ecx, 0FFFFFF80h
0x140016b6a  lea     rdx, aServiceUserDef; "SERVICE_USER_DEFINED_CONTROL"
0x140016b71  cmp     ecx, 7Fh
0x140016b74  lea     rax, aServiceControl_6; "SERVICE_CONTROL_UNKNOWN"
0x140016b7b  cmovbe  rax, rdx
0x140016b7f  retn
0x140016b80  lea     rax, aServiceControl_5; "SERVICE_CONTROL_NETBINDDISABLE"
0x140016b87  retn
0x140016b88  lea     rax, aServiceControl_7; "SERVICE_CONTROL_NETBINDENABLE"
0x140016b8f  retn
0x140016b90  lea     rax, aServiceControl_8; "SERVICE_CONTROL_NETBINDREMOVE"
0x140016b97  retn
0x140016b98  lea     rax, aServiceControl_0; "SERVICE_CONTROL_NETBINDADD"
0x140016b9f  retn
0x140016ba0  lea     rax, aServiceControl_1; "SERVICE_CONTROL_PARAMCHANGE"
0x140016ba7  retn
0x140016ba8  lea     rax, aServiceControl_2; "SERVICE_CONTROL_INTERROGATE"
0x140016baf  retn
0x140016bb0  lea     rax, aServiceControl_4; "SERVICE_CONTROL_CONTINUE"
0x140016bb7  retn
0x140016bb8  lea     rax, aServiceControl; "SERVICE_CONTROL_PAUSE"
0x140016bbf  retn
0x140016bc0  lea     rax, aServiceControl_3; "SERVICE_CONTROL_STOP"
0x140016bc7  retn
```
