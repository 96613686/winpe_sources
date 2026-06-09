# AppListBackupLauncherTelemetry::NullFactory_Error<ushort const (&)[83]>(ushort const (&)[83])

- ea: `0x18000355c`
- end: `0x1800035d0`
- name: `??$NullFactory_Error@AEAY0FD@$$CBG@AppListBackupLauncherTelemetry@@SAXAEAY0FD@$$CBG@Z`
- size: `116`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000dfe0`

## callees

- `0x1800010d0`
- `0x18000355c`
- `0x180009e0c`

## string_xrefs

- `0x180003593`: `UDK API unavailable for IAppListBackupExtensionStatics5, All tiles backup not run.`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall AppListBackupLauncherTelemetry::NullFactory_Error<unsigned short const (&)[83]>(
        __int64 a1)
{
  const struct _tlgProvider_t *result; // rax
  int v2; // r9d
  __int64 v3; // [rsp+40h] [rbp+8h] BYREF
  const wchar_t *v4; // [rsp+48h] [rbp+10h] BYREF

  v3 = a1;
  result = AppListBackupLauncherTelemetry::Provider();
  if ( *(_DWORD *)result > 5u
    && (*((_QWORD *)result + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)result + 3) & 0x400000000000LL) == *((_QWORD *)result + 3) )
  {
    v3 = 0x1000000;
    v4 = L"UDK API unavailable for IAppListBackupExtensionStatics5, All tiles backup not run.";
    return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
                                            (_DWORD)result,
                                            (unsigned int)&byte_18001513F,
                                            0,
                                            v2,
                                            (__int64)&v4,
                                            (__int64)&v3);
  }
  return result;
}

```

## disassembly

```asm
0x18000355c  mov     [rsp+arg_0], rcx
0x180003561  sub     rsp, 38h
0x180003565  call    ?Provider@AppListBackupLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppListBackupLauncherTelemetry::Provider(void)
0x18000356a  mov     ecx, [rax]
0x18000356c  cmp     ecx, 5
0x18000356f  jbe     short loc_1800035CB
0x180003571  mov     rdx, [rax+18h]
0x180003575  mov     r8, 400000000000h
0x18000357f  mov     rcx, [rax+10h]
0x180003583  test    r8, rcx
0x180003586  jz      short loc_1800035CB
0x180003588  mov     rcx, rdx
0x18000358b  and     rcx, r8
0x18000358e  cmp     rcx, rdx
0x180003591  jnz     short loc_1800035CB
0x180003593  lea     rcx, aUdkApiUnavaila_0; "UDK API unavailable for IAppListBackupE"...
0x18000359a  mov     [rsp+38h+arg_0], 1000000h
0x1800035a3  mov     [rsp+38h+arg_8], rcx
0x1800035a8  lea     rdx, byte_18001513F
0x1800035af  lea     rcx, [rsp+38h+arg_0]
0x1800035b4  mov     [rsp+38h+var_10], rcx
0x1800035b9  lea     rcx, [rsp+38h+arg_8]
0x1800035be  mov     [rsp+38h+var_18], rcx
0x1800035c3  mov     rcx, rax
0x1800035c6  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800035cb  add     rsp, 38h
0x1800035cf  retn
```
