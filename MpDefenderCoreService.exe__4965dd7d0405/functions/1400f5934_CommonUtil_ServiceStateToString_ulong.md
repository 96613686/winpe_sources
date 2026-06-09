# CommonUtil::ServiceStateToString(ulong)

- ea: `0x1400f5934`
- end: `0x1400f5997`
- name: `?ServiceStateToString@CommonUtil@@YAPEB_WK@Z`
- size: `99`
- prototype: `const wchar_t *__fastcall(CommonUtil *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140015e60`
- `0x1400166d4`
- `0x1400f5998`
- `0x1400f60dc`

## callees

- `0x1400f5934`

## string_xrefs

- `0x1400f5987`: `SERVICE_START_PENDING`
- `0x1400f598f`: `SERVICE_STOPPED`
- `0x1400f5977`: `SERVICE_RUNNING`
- `0x1400f597f`: `SERVICE_STOP_PENDING`
- `0x1400f5967`: `SERVICE_PAUSE_PENDING`
- `0x1400f596f`: `SERVICE_CONTINUE_PENDING`
- `0x1400f5957`: `SERVICE_UNKNOWN`
- `0x1400f595f`: `SERVICE_PAUSED`

## pseudocode

```c
const wchar_t *__fastcall CommonUtil::ServiceStateToString(CommonUtil *this)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx

  v1 = (_DWORD)this - 1;
  if ( !v1 )
    return L"SERVICE_STOPPED";
  v2 = v1 - 1;
  if ( !v2 )
    return L"SERVICE_START_PENDING";
  v3 = v2 - 1;
  if ( !v3 )
    return L"SERVICE_STOP_PENDING";
  v4 = v3 - 1;
  if ( !v4 )
    return L"SERVICE_RUNNING";
  v5 = v4 - 1;
  if ( !v5 )
    return L"SERVICE_CONTINUE_PENDING";
  v6 = v5 - 1;
  if ( !v6 )
    return L"SERVICE_PAUSE_PENDING";
  if ( v6 == 1 )
    return L"SERVICE_PAUSED";
  return L"SERVICE_UNKNOWN";
}

```

## disassembly

```asm
0x1400f5934  sub     ecx, 1
0x1400f5937  jz      short loc_1400F598F
0x1400f5939  sub     ecx, 1
0x1400f593c  jz      short loc_1400F5987
0x1400f593e  sub     ecx, 1
0x1400f5941  jz      short loc_1400F597F
0x1400f5943  sub     ecx, 1
0x1400f5946  jz      short loc_1400F5977
0x1400f5948  sub     ecx, 1
0x1400f594b  jz      short loc_1400F596F
0x1400f594d  sub     ecx, 1
0x1400f5950  jz      short loc_1400F5967
0x1400f5952  cmp     ecx, 1
0x1400f5955  jz      short loc_1400F595F
0x1400f5957  lea     rax, aServiceUnknown; "SERVICE_UNKNOWN"
0x1400f595e  retn
0x1400f595f  lea     rax, aServicePaused; "SERVICE_PAUSED"
0x1400f5966  retn
0x1400f5967  lea     rax, aServicePausePe; "SERVICE_PAUSE_PENDING"
0x1400f596e  retn
0x1400f596f  lea     rax, aServiceContinu; "SERVICE_CONTINUE_PENDING"
0x1400f5976  retn
0x1400f5977  lea     rax, aServiceRunning; "SERVICE_RUNNING"
0x1400f597e  retn
0x1400f597f  lea     rax, aServiceStopPen; "SERVICE_STOP_PENDING"
0x1400f5986  retn
0x1400f5987  lea     rax, aServiceStartPe; "SERVICE_START_PENDING"
0x1400f598e  retn
0x1400f598f  lea     rax, aServiceStopped; "SERVICE_STOPPED"
0x1400f5996  retn
```
