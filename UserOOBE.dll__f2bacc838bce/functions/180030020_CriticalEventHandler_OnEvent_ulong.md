# CriticalEventHandler::OnEvent(ulong)

- ea: `0x180030020`
- end: `0x180030174`
- name: `?OnEvent@CriticalEventHandler@@UEAAJK@Z`
- size: `340`
- prototype: `__int64 __fastcall(CriticalEventHandler *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000876c`
- `0x18000a664`
- `0x18000a684`
- `0x18000b418`
- `0x18000e270`
- `0x18000e2bc`
- `0x18002f1e8`
- `0x180030020`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800300c6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800300c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CriticalEventHandler::OnEvent(CriticalEventHandler *this, int a2)
{
  char *v4; // rsi
  char v5; // bl
  char *v6; // rbx
  HRESULT Instance; // eax
  int v8; // eax
  const char *v9; // r9
  unsigned int v10; // ebx
  int ppv; // [rsp+20h] [rbp-18h]
  int ppva; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v14; // [rsp+48h] [rbp+10h] BYREF
  char v15; // [rsp+50h] [rbp+18h] BYREF

  v14 = a2;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      v4 = (char *)this + 32;
      wil::AcquireSRWLockShared(&v15, (char *)this + 32);
      v5 = *((_BYTE *)this + 17);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
      if ( !v5 )
      {
        wil::AcquireSRWLockExclusive(&v15, v4);
        try
        {
          v6 = (char *)this + 24;
          if ( !*((_QWORD *)this + 3) )
          {
            *(_QWORD *)v6 = 0;
            Instance = CoCreateInstance(
                         &GUID_2b2cad40_19c1_4794_b32d_397e41d5e8a7,
                         0,
                         1u,
                         &GUID_3853c14b_e028_4cea_93ea_ae9cf14aa9dd,
                         (LPVOID *)this + 3);
            if ( Instance < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x4F,
                (unsigned int)"shell\\oobe\\user\\monitor\\oobemonitoreventhandlers.cpp",
                (const char *)(unsigned int)Instance,
                ppv);
          }
          *((_BYTE *)this + 17) = 1;
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
          v8 = (*(__int64 (**)(void))(**(_QWORD **)v6 + 24LL))();
          v10 = v8;
          if ( v8 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x56,
              (unsigned int)"shell\\oobe\\user\\monitor\\oobemonitoreventhandlers.cpp",
              (const char *)(unsigned int)v8,
              ppv);
            wil::AcquireSRWLockExclusive(&v15, v4);
            *((_BYTE *)this + 17) = 0;
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5A,
              (unsigned int)"shell\\oobe\\user\\monitor\\oobemonitoreventhandlers.cpp",
              (const char *)v10,
              ppva);
          }
        }
        catch ( ... )
        {
          return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0x5F,
                                 (unsigned int)"shell\\oobe\\user\\monitor\\oobemonitoreventhandlers.cpp",
                                 v9);
        }
      }
    }
  }
  else
  {
    wil::AcquireSRWLockExclusive(&v15, (char *)this + 32);
    *((_BYTE *)this + 16) = 0;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  }
  OOBEMonitorTelemetry::OOBEMonitorEvents<unsigned long &>(&v14);
  return 0;
}

```

## disassembly

```asm
0x180030020  mov     rax, rsp
0x180030023  mov     [rax+8], rbx
0x180030027  mov     [rax+20h], rsi
0x18003002b  mov     [rax+10h], edx
0x18003002e  push    rdi
0x18003002f  sub     rsp, 30h
0x180030033  mov     rdi, rcx
0x180030036  test    edx, edx
0x180030038  jnz     short loc_180030067
0x18003003a  lea     rdx, [rcx+20h]
0x18003003e  lea     rcx, [rax+18h]
0x180030042  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180030047  mov     byte ptr [rdi+10h], 0
0x18003004b  lea     rcx, [rsp+38h+arg_10]
0x180030050  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180030055  nop
0x180030056  lea     rcx, [rsp+38h+arg_8]
0x18003005b  call    ??$OOBEMonitorEvents@AEAK@OOBEMonitorTelemetry@@SAXAEAK@Z; OOBEMonitorTelemetry::OOBEMonitorEvents<ulong &>(ulong &)
0x180030060  xor     eax, eax
0x180030062  jmp     loc_180030164
0x180030067  cmp     edx, 1
0x18003006a  jnz     short loc_180030056
0x18003006c  lea     rsi, [rcx+20h]
0x180030070  mov     rdx, rsi
0x180030073  lea     rcx, [rsp+38h+arg_10]
0x180030078  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x18003007d  mov     bl, [rdi+11h]
0x180030080  lea     rcx, [rsp+38h+arg_10]
0x180030085  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003008a  test    bl, bl
0x18003008c  jnz     short loc_180030056
0x18003008e  mov     rdx, rsi
0x180030091  lea     rcx, [rsp+38h+arg_10]
0x180030096  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18003009b  nop
0x18003009c  lea     rbx, [rdi+18h]
0x1800300a0  cmp     qword ptr [rbx], 0
0x1800300a4  jnz     short loc_1800300E9
0x1800300a6  mov     qword ptr [rbx], 0
0x1800300ad  mov     qword ptr [rsp+38h+ppv], rbx; int
0x1800300b2  lea     r9, _GUID_3853c14b_e028_4cea_93ea_ae9cf14aa9dd; riid
0x1800300b9  xor     edx, edx; pUnkOuter
0x1800300bb  lea     r8d, [rdx+1]; dwClsContext
0x1800300bf  lea     rcx, _GUID_2b2cad40_19c1_4794_b32d_397e41d5e8a7; rclsid
0x1800300c6  call    cs:__imp_CoCreateInstance
0x1800300cc  mov     rcx, [rsp+38h]; this
0x1800300d1  test    eax, eax
0x1800300d3  jns     short loc_1800300E9
0x1800300d5  mov     r9d, eax; char *
0x1800300d8  lea     r8, aShellOobeUserM; "shell\\oobe\\user\\monitor\\oobemonitor"...
0x1800300df  mov     edx, 4Fh ; 'O'; void *
0x1800300e4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800300e9  mov     byte ptr [rdi+11h], 1
0x1800300ed  lea     rcx, [rsp+38h+arg_10]
0x1800300f2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800300f7  mov     rcx, [rbx]
0x1800300fa  mov     r8, [rcx]
0x1800300fd  mov     al, [rdi+10h]
0x180030100  neg     al
0x180030102  sbb     edx, edx
0x180030104  neg     edx
0x180030106  inc     edx
0x180030108  mov     rax, [r8+18h]
0x18003010c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030111  mov     ebx, eax
0x180030113  mov     rcx, [rsp+38h]; this
0x180030118  test    eax, eax
0x18003011a  jns     loc_180030056
0x180030120  mov     r9d, eax; char *
0x180030123  lea     r8, aShellOobeUserM; "shell\\oobe\\user\\monitor\\oobemonitor"...
0x18003012a  mov     edx, 56h ; 'V'; void *
0x18003012f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030134  mov     rdx, rsi
0x180030137  lea     rcx, [rsp+38h+arg_10]
0x18003013c  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180030141  nop
0x180030142  mov     byte ptr [rdi+11h], 0
0x180030146  mov     rcx, [rsp+38h]; this
0x18003014b  mov     r9d, ebx; char *
0x18003014e  lea     r8, aShellOobeUserM; "shell\\oobe\\user\\monitor\\oobemonitor"...
0x180030155  mov     edx, 5Ah ; 'Z'; void *
0x18003015a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030160  mov     eax, [rsp+38h+arg_8]
0x180030164  mov     rbx, [rsp+38h+arg_0]
0x180030169  mov     rsi, [rsp+38h+arg_18]
0x18003016e  add     rsp, 30h
0x180030172  pop     rdi
0x180030173  retn
```
