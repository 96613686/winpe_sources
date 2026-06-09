# Windows::FileSystem::ReFs::ServiceControlName(ulong)

- ea: `0x140030e40`
- end: `0x140030f62`
- name: `?ServiceControlName@ReFs@FileSystem@Windows@@YAPEBGK@Z`
- size: `290`
- prototype: `const unsigned __int16 *__fastcall(Windows::FileSystem::ReFs *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140031188`

## callees

- `0x140030e40`

## string_xrefs

- `0x140030eb8`: `SERVICE_CONTROL_PAUSE`
- `0x140030ec1`: `SERVICE_CONTROL_STOP`
- `0x140030ea6`: `SERVICE_CONTROL_INTERROGATE`
- `0x140030eaf`: `SERVICE_CONTROL_CONTINUE`
- `0x140030e94`: `SERVICE_CONTROL_PARAMCHANGE`
- `0x140030e9d`: `SERVICE_CONTROL_SHUTDOWN`
- `0x140030e82`: `SERVICE_CONTROL_NETBINDREMOVE`
- `0x140030e8b`: `SERVICE_CONTROL_NETBINDADD`
- `0x140030f2c`: `SERVICE_CONTROL_NETBINDDISABLE`
- `0x140030eca`: `SERVICE_CONTROL_NETBINDENABLE`
- `0x140030f1a`: `SERVICE_CONTROL_HARDWAREPROFILECHANGE`
- `0x140030f23`: `SERVICE_CONTROL_DEVICEEVENT`
- `0x140030f08`: `SERVICE_CONTROL_SESSIONCHANGE`
- `0x140030f11`: `SERVICE_CONTROL_POWEREVENT`
- `0x140030ef6`: `SERVICE_CONTROL_TIMECHANGE`
- `0x140030eff`: `SERVICE_CONTROL_PRESHUTDOWN`
- `0x140030f5a`: `SERVICE_CONTROL_LOWRESOURCES`
- `0x140030f35`: `SERVICE_CONTROL_TRIGGEREVENT`
- `0x140030f51`: `SERVICE_CONTROL_SYSTEMLOWRESOURCES`

## pseudocode

```c
const unsigned __int16 *__fastcall Windows::FileSystem::ReFs::ServiceControlName(Windows::FileSystem::ReFs *this)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx

  if ( (unsigned int)this <= 0x20 )
  {
    if ( (_DWORD)this == 32 )
      return L"SERVICE_CONTROL_TRIGGEREVENT";
    if ( (unsigned int)this > 9 )
    {
      v9 = (_DWORD)this - 10;
      if ( !v9 )
        return L"SERVICE_CONTROL_NETBINDDISABLE";
      v10 = v9 - 1;
      if ( !v10 )
        return L"SERVICE_CONTROL_DEVICEEVENT";
      v11 = v10 - 1;
      if ( !v11 )
        return L"SERVICE_CONTROL_HARDWAREPROFILECHANGE";
      v12 = v11 - 1;
      if ( !v12 )
        return L"SERVICE_CONTROL_POWEREVENT";
      v13 = v12 - 1;
      if ( !v13 )
        return L"SERVICE_CONTROL_SESSIONCHANGE";
      v14 = v13 - 1;
      if ( !v14 )
        return L"SERVICE_CONTROL_PRESHUTDOWN";
      if ( v14 == 1 )
        return L"SERVICE_CONTROL_TIMECHANGE";
    }
    else
    {
      if ( (_DWORD)this == 9 )
        return L"SERVICE_CONTROL_NETBINDENABLE";
      v1 = (_DWORD)this - 1;
      if ( !v1 )
        return L"SERVICE_CONTROL_STOP";
      v2 = v1 - 1;
      if ( !v2 )
        return L"SERVICE_CONTROL_PAUSE";
      v3 = v2 - 1;
      if ( !v3 )
        return L"SERVICE_CONTROL_CONTINUE";
      v4 = v3 - 1;
      if ( !v4 )
        return L"SERVICE_CONTROL_INTERROGATE";
      v5 = v4 - 1;
      if ( !v5 )
        return L"SERVICE_CONTROL_SHUTDOWN";
      v6 = v5 - 1;
      if ( !v6 )
        return L"SERVICE_CONTROL_PARAMCHANGE";
      v7 = v6 - 1;
      if ( !v7 )
        return L"SERVICE_CONTROL_NETBINDADD";
      if ( v7 == 1 )
        return L"SERVICE_CONTROL_NETBINDREMOVE";
    }
    return L"Unknown";
  }
  v15 = (_DWORD)this - 96;
  if ( !v15 )
    return L"SERVICE_CONTROL_LOWRESOURCES";
  if ( v15 != 1 )
    return L"Unknown";
  return L"SERVICE_CONTROL_SYSTEMLOWRESOURCES";
}

```

## disassembly

```asm
0x140030e40  cmp     ecx, 20h ; ' '
0x140030e43  ja      loc_140030F3E
0x140030e49  jz      loc_140030F35
0x140030e4f  cmp     ecx, 9
0x140030e52  ja      short loc_140030ED3
0x140030e54  jz      short loc_140030ECA
0x140030e56  sub     ecx, 1
0x140030e59  jz      short loc_140030EC1
0x140030e5b  sub     ecx, 1
0x140030e5e  jz      short loc_140030EB8
0x140030e60  sub     ecx, 1
0x140030e63  jz      short loc_140030EAF
0x140030e65  sub     ecx, 1
0x140030e68  jz      short loc_140030EA6
0x140030e6a  sub     ecx, 1
0x140030e6d  jz      short loc_140030E9D
0x140030e6f  sub     ecx, 1
0x140030e72  jz      short loc_140030E94
0x140030e74  sub     ecx, 1
0x140030e77  jz      short loc_140030E8B
0x140030e79  cmp     ecx, 1
0x140030e7c  jnz     loc_140030F48
0x140030e82  lea     rax, aServiceControl_16; "SERVICE_CONTROL_NETBINDREMOVE"
0x140030e89  retn
0x140030e8b  lea     rax, aServiceControl_2; "SERVICE_CONTROL_NETBINDADD"
0x140030e92  retn
0x140030e94  lea     rax, aServiceControl_3; "SERVICE_CONTROL_PARAMCHANGE"
0x140030e9b  retn
0x140030e9d  lea     rax, aServiceControl_4; "SERVICE_CONTROL_SHUTDOWN"
0x140030ea4  retn
0x140030ea6  lea     rax, aServiceControl_5; "SERVICE_CONTROL_INTERROGATE"
0x140030ead  retn
0x140030eaf  lea     rax, aServiceControl_10; "SERVICE_CONTROL_CONTINUE"
0x140030eb6  retn
0x140030eb8  lea     rax, aServiceControl_1; "SERVICE_CONTROL_PAUSE"
0x140030ebf  retn
0x140030ec1  lea     rax, aServiceControl_9; "SERVICE_CONTROL_STOP"
0x140030ec8  retn
0x140030eca  lea     rax, aServiceControl_15; "SERVICE_CONTROL_NETBINDENABLE"
0x140030ed1  retn
0x140030ed3  sub     ecx, 0Ah
0x140030ed6  jz      short loc_140030F2C
0x140030ed8  sub     ecx, 1
0x140030edb  jz      short loc_140030F23
0x140030edd  sub     ecx, 1
0x140030ee0  jz      short loc_140030F1A
0x140030ee2  sub     ecx, 1
0x140030ee5  jz      short loc_140030F11
0x140030ee7  sub     ecx, 1
0x140030eea  jz      short loc_140030F08
0x140030eec  sub     ecx, 1
0x140030eef  jz      short loc_140030EFF
0x140030ef1  cmp     ecx, 1
0x140030ef4  jnz     short loc_140030F48
0x140030ef6  lea     rax, aServiceControl_12; "SERVICE_CONTROL_TIMECHANGE"
0x140030efd  retn
0x140030eff  lea     rax, aServiceControl_8; "SERVICE_CONTROL_PRESHUTDOWN"
0x140030f06  retn
0x140030f08  lea     rax, aServiceControl_17; "SERVICE_CONTROL_SESSIONCHANGE"
0x140030f0f  retn
0x140030f11  lea     rax, aServiceControl_0; "SERVICE_CONTROL_POWEREVENT"
0x140030f18  retn
0x140030f1a  lea     rax, aServiceControl_7; "SERVICE_CONTROL_HARDWAREPROFILECHANGE"
0x140030f21  retn
0x140030f23  lea     rax, aServiceControl_14; "SERVICE_CONTROL_DEVICEEVENT"
0x140030f2a  retn
0x140030f2c  lea     rax, aServiceControl_11; "SERVICE_CONTROL_NETBINDDISABLE"
0x140030f33  retn
0x140030f35  lea     rax, aServiceControl; "SERVICE_CONTROL_TRIGGEREVENT"
0x140030f3c  retn
0x140030f3e  sub     ecx, 60h ; '`'
0x140030f41  jz      short loc_140030F5A
0x140030f43  cmp     ecx, 1
0x140030f46  jz      short loc_140030F51
0x140030f48  lea     rax, aUnknown; "Unknown"
0x140030f4f  retn
0x140030f51  lea     rax, aServiceControl_13; "SERVICE_CONTROL_SYSTEMLOWRESOURCES"
0x140030f58  retn
0x140030f5a  lea     rax, aServiceControl_6; "SERVICE_CONTROL_LOWRESOURCES"
0x140030f61  retn
```
