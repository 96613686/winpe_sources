# Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance(void)

- ea: `0x140042d28`
- end: `0x140042e26`
- name: `?Instance@?$Singleton@VConfigurationValuesClass@ClientConfiguration@AppV@@@@SAAEAVConfigurationValuesClass@ClientConfiguration@AppV@@XZ`
- size: `254`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140045328`
- `0x140058258`
- `0x140058b9c`

## callees

- `0x1400042a4`
- `0x140042d28`
- `0x140042e2c`
- `0x140043348`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140042d76`
- `KERNEL32!GetCurrentThreadId` at `0x140042d76`
- `KERNEL32!LeaveCriticalSection` at `0x140042e0e`
- `KERNEL32!LeaveCriticalSection` at `0x140042e0e`
- `KERNEL32!EnterCriticalSection` at `0x140042d5d`
- `KERNEL32!EnterCriticalSection` at `0x140042d5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance()
{
  __int64 result; // rax
  int v1; // eax
  AppV::ClientConfiguration::ConfigurationValuesClass *v2; // [rsp+50h] [rbp+8h]

  result = `Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance'::`2'::s_instance;
  if ( !`Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance'::`2'::s_instance )
  {
    EnterCriticalSection(&Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::s_cs);
    v1 = qword_1400B14A0 + 1;
    LODWORD(qword_1400B14A0) = v1;
    if ( v1 == 1 )
    {
      HIDWORD(qword_1400B14A0) = GetCurrentThreadId();
      v1 = qword_1400B14A0;
    }
    try
    {
      if ( !`Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance'::`2'::s_instance )
      {
        v2 = (AppV::ClientConfiguration::ConfigurationValuesClass *)operator new(0x30u);
        *(_QWORD *)v2 = 0;
        *((_QWORD *)v2 + 1) = 0;
        *((_QWORD *)v2 + 2) = 0;
        *((_QWORD *)v2 + 3) = 0;
        *((_QWORD *)v2 + 4) = 0;
        *((_QWORD *)v2 + 5) = 0;
        AppV::ClientConfiguration::ConfigurationValuesClass::KnownConfigurationRootsTableInit(v2);
        AppV::ClientConfiguration::ConfigurationValuesClass::KnownConfigurationValuesTableInit(v2);
        `Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance'::`2'::s_instance = (__int64)v2;
        v1 = qword_1400B14A0;
      }
      LODWORD(qword_1400B14A0) = v1 - 1;
      if ( v1 == 1 )
        qword_1400B14A0 = 0;
      LeaveCriticalSection(&Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::s_cs);
      result = `Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance'::`2'::s_instance;
    }
    catch ( ... )
    {
      throw;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140042d28  mov     [rsp+arg_8], rbx
0x140042d2d  push    rsi
0x140042d2e  sub     rsp, 40h
0x140042d32  mov     rax, cs:?s_instance@?1??Instance@?$Singleton@VConfigurationValuesClass@ClientConfiguration@AppV@@@@SAAEAVConfigurationValuesClass@ClientConfiguration@AppV@@XZ@4PEAV345@EA; AppV::ClientConfiguration::ConfigurationValuesClass * `Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance(void)'::`2'::s_instance
0x140042d39  test    rax, rax
0x140042d3c  jnz     loc_140042E1B
0x140042d42  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x140042d49  mov     [rsp+48h+var_28], rax
0x140042d4e  lea     rsi, ?s_cs@?$Singleton@VConfigurationValuesClass@ClientConfiguration@AppV@@@@0Vcritical_section@shared@softricity@@A; softricity::shared::critical_section Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::s_cs
0x140042d55  mov     [rsp+48h+var_18], rsi
0x140042d5a  mov     rcx, rsi; lpCriticalSection
0x140042d5d  call    cs:__imp_EnterCriticalSection
0x140042d63  mov     eax, dword ptr cs:qword_1400B14A0
0x140042d69  inc     eax
0x140042d6b  mov     dword ptr cs:qword_1400B14A0, eax
0x140042d71  cmp     eax, 1
0x140042d74  jnz     short loc_140042D88
0x140042d76  call    cs:__imp_GetCurrentThreadId
0x140042d7c  mov     dword ptr cs:qword_1400B14A0+4, eax
0x140042d82  mov     eax, dword ptr cs:qword_1400B14A0
0x140042d88  mov     [rsp+48h+var_20], 1
0x140042d8d  cmp     cs:?s_instance@?1??Instance@?$Singleton@VConfigurationValuesClass@ClientConfiguration@AppV@@@@SAAEAVConfigurationValuesClass@ClientConfiguration@AppV@@XZ@4PEAV345@EA, 0; AppV::ClientConfiguration::ConfigurationValuesClass * `Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance(void)'::`2'::s_instance
0x140042d95  jnz     short loc_140042DF6
0x140042d97  mov     ecx, 30h ; '0'; Size
0x140042d9c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140042da1  mov     rbx, rax
0x140042da4  mov     [rsp+48h+arg_0], rax
0x140042da9  mov     qword ptr [rax], 0
0x140042db0  mov     qword ptr [rax+8], 0
0x140042db8  mov     qword ptr [rax+10h], 0
0x140042dc0  mov     qword ptr [rax+18h], 0
0x140042dc8  mov     qword ptr [rax+20h], 0
0x140042dd0  mov     qword ptr [rax+28h], 0
0x140042dd8  mov     rcx, rax; this
0x140042ddb  call    ?KnownConfigurationRootsTableInit@ConfigurationValuesClass@ClientConfiguration@AppV@@AEAAXXZ; AppV::ClientConfiguration::ConfigurationValuesClass::KnownConfigurationRootsTableInit(void)
0x140042de0  mov     rcx, rbx; this
0x140042de3  call    ?KnownConfigurationValuesTableInit@ConfigurationValuesClass@ClientConfiguration@AppV@@AEAAXXZ; AppV::ClientConfiguration::ConfigurationValuesClass::KnownConfigurationValuesTableInit(void)
0x140042de8  nop
0x140042de9  mov     cs:?s_instance@?1??Instance@?$Singleton@VConfigurationValuesClass@ClientConfiguration@AppV@@@@SAAEAVConfigurationValuesClass@ClientConfiguration@AppV@@XZ@4PEAV345@EA, rbx; AppV::ClientConfiguration::ConfigurationValuesClass * `Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance(void)'::`2'::s_instance
0x140042df0  mov     eax, dword ptr cs:qword_1400B14A0
0x140042df6  sub     eax, 1
0x140042df9  mov     dword ptr cs:qword_1400B14A0, eax
0x140042dff  jnz     short loc_140042E0B
0x140042e01  mov     dword ptr cs:qword_1400B14A0+4, 0
0x140042e0b  mov     rcx, rsi; lpCriticalSection
0x140042e0e  call    cs:__imp_LeaveCriticalSection
0x140042e14  mov     rax, cs:?s_instance@?1??Instance@?$Singleton@VConfigurationValuesClass@ClientConfiguration@AppV@@@@SAAEAVConfigurationValuesClass@ClientConfiguration@AppV@@XZ@4PEAV345@EA; AppV::ClientConfiguration::ConfigurationValuesClass * `Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance(void)'::`2'::s_instance
0x140042e1b  mov     rbx, [rsp+48h+arg_8]
0x140042e20  add     rsp, 40h
0x140042e24  pop     rsi
0x140042e25  retn
```
