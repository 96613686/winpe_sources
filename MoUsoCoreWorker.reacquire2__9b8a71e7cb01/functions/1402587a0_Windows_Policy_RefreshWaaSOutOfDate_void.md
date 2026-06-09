# Windows::Policy::RefreshWaaSOutOfDate(void)

- ea: `0x1402587a0`
- end: `0x140258f6f`
- name: `?RefreshWaaSOutOfDate@Policy@Windows@@AEAAXXZ`
- size: `1999`
- prototype: `void __fastcall(Windows::Policy *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140259330`
- `0x140259360`
- `0x140259380`

## callees

- `0x1400413a8`
- `0x1400a5368`
- `0x14012d864`
- `0x140258710`
- `0x1402587a0`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140258856`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140258856`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140258801`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140258a00`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140258eb3`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140258801`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140258a00`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140258eb3`

## string_xrefs

- `0x140258c1b`: `Override out of date value for feature update based on WaaS because it is a managed device.`
- `0x140258b1e`: `Override out of date value for quality update based on WaaS because it is a managed device.`
- `0x140258f20`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Policy.cpp`
- `0x140258f34`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Policy.cpp`
- `0x140258f48`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Policy.cpp`
- `0x140258f5c`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Policy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Windows::Policy::RefreshWaaSOutOfDate(Windows::Policy *this)
{
  char v2; // bl
  const char *v3; // r9
  __int64 v4; // rdi
  signed __int64 v5; // rdx
  HRESULT v6; // r14d
  _QWORD **System; // rax
  char v8; // r15
  volatile signed __int32 *v9; // rdi
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  volatile signed __int32 *v12; // rdi
  volatile signed __int32 *v13; // rdi
  signed __int64 v14; // r8
  int v15; // eax
  int v16; // eax
  int v17; // eax
  _QWORD *v18; // rax
  _QWORD *v19; // rax
  char v20; // r14
  volatile signed __int32 *v21; // rdi
  volatile signed __int32 *v22; // rdi
  int *v23; // rdx
  int v24; // eax
  _QWORD *v25; // rax
  _QWORD *v26; // rax
  char v27; // r14
  volatile signed __int32 *v28; // rdi
  volatile signed __int32 *v29; // rdi
  char v30; // r8
  int v31; // ecx
  int ppv; // [rsp+20h] [rbp-C8h]
  const wchar_t *v33; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+48h] [rbp-A0h]
  _BYTE v35[8]; // [rsp+50h] [rbp-98h] BYREF
  volatile signed __int32 *v36; // [rsp+58h] [rbp-90h]
  int v37; // [rsp+60h] [rbp-88h] BYREF
  int v38; // [rsp+64h] [rbp-84h] BYREF
  LPVOID v39; // [rsp+68h] [rbp-80h] BYREF
  int v40; // [rsp+70h] [rbp-78h] BYREF
  __int64 v41; // [rsp+78h] [rbp-70h] BYREF
  int v42; // [rsp+80h] [rbp-68h]
  int v43; // [rsp+88h] [rbp-60h] BYREF
  char v44; // [rsp+8Ch] [rbp-5Ch]
  __int64 v45; // [rsp+90h] [rbp-58h] BYREF
  __int64 v46; // [rsp+98h] [rbp-50h] BYREF
  int v47; // [rsp+A0h] [rbp-48h]
  __int64 v48; // [rsp+A8h] [rbp-40h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v2 = 0;
  LODWORD(v33) = 0;
  try
  {
    if ( Windows::Policy::DisableAllUnmanagedUpdateServicesWhenWsus(this) )
      return;
    v4 = *((_QWORD *)this + 3) + 864000000000LL;
    v33 = 0;
    GetSystemTimePreciseAsFileTime(&v33);
    v5 = (unsigned int)v33 + ((unsigned __int64)HIDWORD(v33) << 32) - 116444736000000000LL;
    if ( v4 != v5 && v4 >= v5 )
      return;
    v39 = 0;
    v6 = CoCreateInstance(
           &GUID_098ef871_fa9f_46af_8958_c083515d7c9c,
           0,
           1u,
           &GUID_28f36eb8_3990_460a_bda9_3f06f8514de9,
           &v39);
    if ( v6 != -2147221164
      || (System = (_QWORD **)SystemInterface::Service::GetSystem(v35),
          v2 = 1,
          LODWORD(v33) = 1,
          v8 = 1,
          !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**System + 168LL))(*System, **System)) )
    {
      v8 = 0;
    }
    if ( (v2 & 1) != 0 )
    {
      v9 = v36;
      if ( v36 )
      {
        if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
          if ( !_InterlockedDecrement(v9 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        }
      }
    }
    if ( v8 )
    {
      if ( v39 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39 + 16LL))(v39);
      return;
    }
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3A4,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Policy.cpp",
        (const char *)(unsigned int)v6,
        ppv);
    v45 = 0;
    v38 = 0;
    v37 = 0;
    v41 = 0;
    v42 = 0;
    v10 = (_QWORD *)SystemInterface::Service::GetSystem(&v33);
    v11 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v10 + 48LL))(*v10, v35);
    (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v11 + 72LL))(*v11, &v43);
    v12 = v36;
    if ( v36 )
    {
      if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    v13 = (volatile signed __int32 *)v34;
    if ( v34 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v34 + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    if ( v44 )
    {
      v38 = 1;
      v33 = 0;
      GetSystemTimePreciseAsFileTime(&v33);
      v14 = (unsigned int)v33 + ((unsigned __int64)HIDWORD(v33) << 32) - 36000000000LL * (v43 + 3234576LL);
      v45 = v14 % 10000000 + 10000000 * (v14 / 10000000 + 0x2B6109100LL);
LABEL_34:
      if ( (_DWORD)v41 == 9 )
      {
        v33 = L"Override out of date value for quality update based on WaaS because it is a managed device.";
        v34 = 91;
        SystemInterface::Log<>(&v33);
        *((_BYTE *)this + 17) = 0;
      }
      else if ( v38 && !v37 )
      {
        *((_BYTE *)this + 17) = HIDWORD(v41) == 3;
      }
LABEL_39:
      v48 = 0;
      v38 = 0;
      v37 = 0;
      v46 = 0;
      v47 = 0;
      v16 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, int *))(*(_QWORD *)v39 + 88LL))(
              v39,
              &v48,
              &v46,
              &v38);
      if ( v16 == -2147024894 )
      {
        v33 = L"Waas assessor returned file not found, exiting gracefully.";
        v34 = 58;
        SystemInterface::Log<>(&v33);
        if ( v39 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39 + 16LL))(v39);
      }
      else
      {
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3E7,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Policy.cpp",
            (const char *)(unsigned int)v16,
            (int)&v37);
        if ( v16 != 1 )
        {
          if ( (_DWORD)v46 == 9 )
          {
            v33 = L"Override out of date value for feature update based on WaaS because it is a managed device.";
            v34 = 91;
            SystemInterface::Log<>(&v33);
            *((_BYTE *)this + 16) = 0;
          }
          else if ( v38 && !v37 )
          {
            *((_BYTE *)this + 16) = HIDWORD(v41) == 3;
          }
        }
        v49 = 0;
        v40 = 0;
        v17 = (*(__int64 (__fastcall **)(LPVOID, int *, int *, __int64 *))(*(_QWORD *)v39 + 80LL))(
                v39,
                &v37,
                &v40,
                &v49);
        if ( v17 == -2147024894 )
        {
          v33 = L"Waas assessor returned file not found, exiting gracefully.";
          v34 = 58;
          SystemInterface::Log<>(&v33);
          if ( v39 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39 + 16LL))(v39);
        }
        else
        {
          if ( v17 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x400,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Policy.cpp",
              (const char *)(unsigned int)v17,
              1);
          if ( v17 == 1 )
          {
            v37 = 0;
            v40 = 876000;
          }
          v18 = (_QWORD *)SystemInterface::Service::GetSystem(&v33);
          v19 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v18 + 48LL))(*v18, v35);
          v20 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 144LL))(*v19);
          v21 = v36;
          if ( v36 )
          {
            if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
              if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
            }
          }
          v22 = (volatile signed __int32 *)v34;
          if ( v34 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v34 + 8), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
              if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
            }
          }
          if ( v20 )
          {
            v23 = (int *)((char *)this + 8);
            if ( !*((_BYTE *)this + 12) )
              *((_BYTE *)this + 12) = 1;
            v24 = 0;
          }
          else
          {
            v25 = (_QWORD *)SystemInterface::Service::GetSystem(&v33);
            v26 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v25 + 48LL))(*v25, v35);
            v27 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 136LL))(*v26);
            v28 = v36;
            if ( v36 )
            {
              if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
                if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
              }
            }
            v29 = (volatile signed __int32 *)v34;
            if ( v34 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v34 + 8), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
                if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
              }
            }
            v23 = (int *)((char *)this + 8);
            v30 = *((_BYTE *)this + 12);
            if ( v27 )
            {
              if ( !v30 )
                *((_BYTE *)this + 12) = 1;
              v24 = 120;
            }
            else
            {
              v31 = v40;
              if ( v37 )
                v31 = -v40;
              v24 = 24 * v31;
              if ( !v30 )
                *((_BYTE *)this + 12) = 1;
            }
          }
          *v23 = v24;
          v33 = 0;
          GetSystemTimePreciseAsFileTime(&v33);
          *((_QWORD *)this + 3) = ((unsigned __int64)HIDWORD(v33) << 32) - 116444736000000000LL + (unsigned int)v33;
          if ( v39 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39 + 16LL))(v39);
        }
      }
      return;
    }
    v15 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, int *))(*(_QWORD *)v39 + 88LL))(
            v39,
            &v45,
            &v41,
            &v38);
    if ( v15 != -2147024894 )
    {
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3C5,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Policy.cpp",
          (const char *)(unsigned int)v15,
          (int)&v37);
      if ( v15 == 1 )
        goto LABEL_39;
      goto LABEL_34;
    }
    v33 = L"Waas assessor returned file not found, exiting gracefully.";
    v34 = 58;
    SystemInterface::Log<>(&v33);
    if ( v39 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39 + 16LL))(v39);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x41A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Policy.cpp",
      v3);
  }
}

```

## disassembly

```asm
0x1402587a0  mov     [rsp+arg_8], rbx
0x1402587a5  mov     [rsp+arg_10], rsi
0x1402587aa  push    rdi
0x1402587ab  push    r12
0x1402587ad  push    r13
0x1402587af  push    r14
0x1402587b1  push    r15
0x1402587b3  sub     rsp, 0C0h
0x1402587ba  mov     rax, cs:__security_cookie
0x1402587c1  xor     rax, rsp
0x1402587c4  mov     [rsp+0E8h+var_30], rax
0x1402587cc  mov     rsi, rcx
0x1402587cf  xor     r12d, r12d
0x1402587d2  mov     ebx, r12d
0x1402587d5  mov     dword ptr [rsp+0E8h+var_A8], ebx
0x1402587d9  call    ?DisableAllUnmanagedUpdateServicesWhenWsus@Policy@Windows@@UEAA_NXZ; Windows::Policy::DisableAllUnmanagedUpdateServicesWhenWsus(void)
0x1402587de  test    al, al
0x1402587e0  jnz     loc_140258EF0
0x1402587e6  mov     rdi, [rsi+18h]
0x1402587ea  mov     rcx, 0C92A69C000h
0x1402587f4  add     rdi, rcx
0x1402587f7  mov     [rsp+0E8h+var_A8], r12
0x1402587fc  lea     rcx, [rsp+0E8h+var_A8]
0x140258801  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x140258807  mov     eax, dword ptr [rsp+0E8h+var_A8+4]
0x14025880b  shl     rax, 20h
0x14025880f  mov     ecx, dword ptr [rsp+0E8h+var_A8]
0x140258813  mov     rdx, 0FE624E212AC18000h
0x14025881d  add     rdx, rax
0x140258820  add     rdx, rcx
0x140258823  cmp     rdi, rdx
0x140258826  jz      short loc_14025882E
0x140258828  jge     loc_140258EF0
0x14025882e  mov     [rsp+0E8h+var_80], r12
0x140258833  lea     rax, [rsp+0E8h+var_80]
0x140258838  mov     [rsp+0E8h+ppv], rax; int
0x14025883d  lea     r9, _GUID_28f36eb8_3990_460a_bda9_3f06f8514de9; riid
0x140258844  mov     r13d, 1
0x14025884a  mov     r8d, r13d; dwClsContext
0x14025884d  xor     edx, edx; pUnkOuter
0x14025884f  lea     rcx, _GUID_098ef871_fa9f_46af_8958_c083515d7c9c; rclsid
0x140258856  call    cs:__imp_CoCreateInstance
0x14025885c  mov     r14d, eax
0x14025885f  cmp     eax, 80040154h
0x140258864  jnz     short loc_140258891
0x140258866  lea     rcx, [rsp+0E8h+var_98]
0x14025886b  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x140258870  nop
0x140258871  mov     ebx, r13d
0x140258874  mov     dword ptr [rsp+0E8h+var_A8], ebx
0x140258878  mov     rcx, [rax]
0x14025887b  mov     rdx, [rcx]
0x14025887e  mov     rax, [rdx+0A8h]
0x140258885  call    _guard_dispatch_icall
0x14025888a  test    al, al
0x14025888c  mov     r15b, r13b
0x14025888f  jnz     short loc_140258894
0x140258891  mov     r15b, r12b
0x140258894  test    r13b, bl
0x140258897  jz      short loc_1402588DB
0x140258899  mov     rdi, [rsp+0E8h+var_90]
0x14025889e  test    rdi, rdi
0x1402588a1  jz      short loc_1402588DB
0x1402588a3  or      ebx, 0FFFFFFFFh
0x1402588a6  mov     eax, ebx
0x1402588a8  lock xadd [rdi+8], eax
0x1402588ad  add     eax, ebx
0x1402588af  jnz     short loc_1402588DE
0x1402588b1  mov     rax, [rdi]
0x1402588b4  mov     rcx, rdi
0x1402588b7  mov     rax, [rax]
0x1402588ba  call    _guard_dispatch_icall
0x1402588bf  mov     eax, ebx
0x1402588c1  lock xadd [rdi+0Ch], eax
0x1402588c6  add     eax, ebx
0x1402588c8  jnz     short loc_1402588DE
0x1402588ca  mov     rax, [rdi]
0x1402588cd  mov     rcx, rdi
0x1402588d0  mov     rax, [rax+8]
0x1402588d4  call    _guard_dispatch_icall
0x1402588d9  jmp     short loc_1402588DE
0x1402588db  or      ebx, 0FFFFFFFFh
0x1402588de  test    r15b, r15b
0x1402588e1  jz      short loc_1402588FF
0x1402588e3  mov     rcx, [rsp+0E8h+var_80]
0x1402588e8  test    rcx, rcx
0x1402588eb  jz      short loc_1402588FA
0x1402588ed  mov     rax, [rcx]
0x1402588f0  mov     rax, [rax+10h]
0x1402588f4  call    _guard_dispatch_icall
0x1402588f9  nop
0x1402588fa  jmp     loc_140258EF0
0x1402588ff  mov     rcx, [rsp+0E8h]; this
0x140258907  test    r14d, r14d
0x14025890a  js      loc_140258F1D
0x140258910  mov     [rsp+0E8h+var_58], r12
0x140258918  mov     [rsp+0E8h+var_84], r12d
0x14025891d  mov     [rsp+0E8h+var_88], r12d
0x140258922  xor     eax, eax
0x140258924  mov     [rsp+0E8h+var_70], rax
0x140258929  mov     [rsp+0E8h+var_68], eax
0x140258930  lea     rcx, [rsp+0E8h+var_A8]
0x140258935  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x14025893a  nop
0x14025893b  mov     rcx, [rax]
0x14025893e  mov     rax, [rcx]
0x140258941  lea     rdx, [rsp+0E8h+var_98]
0x140258946  mov     rax, [rax+30h]
0x14025894a  call    _guard_dispatch_icall
0x14025894f  nop
0x140258950  mov     rcx, [rax]
0x140258953  mov     rax, [rcx]
0x140258956  lea     rdx, [rsp+0E8h+var_60]
0x14025895e  mov     rax, [rax+48h]
0x140258962  call    _guard_dispatch_icall
0x140258967  nop
0x140258968  mov     rdi, [rsp+0E8h+var_90]
0x14025896d  test    rdi, rdi
0x140258970  jz      short loc_1402589A6
0x140258972  mov     eax, ebx
0x140258974  lock xadd [rdi+8], eax
0x140258979  add     eax, ebx
0x14025897b  jnz     short loc_1402589A6
0x14025897d  mov     rax, [rdi]
0x140258980  mov     rcx, rdi
0x140258983  mov     rax, [rax]
0x140258986  call    _guard_dispatch_icall
0x14025898b  mov     eax, ebx
0x14025898d  lock xadd [rdi+0Ch], eax
0x140258992  add     eax, ebx
0x140258994  jnz     short loc_1402589A6
0x140258996  mov     rax, [rdi]
0x140258999  mov     rcx, rdi
0x14025899c  mov     rax, [rax+8]
0x1402589a0  call    _guard_dispatch_icall
0x1402589a5  nop
0x1402589a6  mov     rdi, [rsp+0E8h+var_A0]
0x1402589ab  test    rdi, rdi
0x1402589ae  jz      short loc_1402589E3
0x1402589b0  mov     eax, ebx
0x1402589b2  lock xadd [rdi+8], eax
0x1402589b7  add     eax, ebx
0x1402589b9  jnz     short loc_1402589E3
0x1402589bb  mov     rax, [rdi]
0x1402589be  mov     rcx, rdi
0x1402589c1  mov     rax, [rax]
0x1402589c4  call    _guard_dispatch_icall
0x1402589c9  mov     eax, ebx
0x1402589cb  lock xadd [rdi+0Ch], eax
0x1402589d0  add     eax, ebx
0x1402589d2  jnz     short loc_1402589E3
0x1402589d4  mov     rax, [rdi]
0x1402589d7  mov     rcx, rdi
0x1402589da  mov     rax, [rax+8]
0x1402589de  call    _guard_dispatch_icall
0x1402589e3  cmp     [rsp+0E8h+var_5C], r12b
0x1402589eb  jz      loc_140258A86
0x1402589f1  mov     [rsp+0E8h+var_84], r13d
0x1402589f6  mov     [rsp+0E8h+var_A8], r12
0x1402589fb  lea     rcx, [rsp+0E8h+var_A8]
0x140258a00  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x140258a06  movsxd  rax, [rsp+0E8h+var_60]
0x140258a0e  add     rax, 315B10h
0x140258a14  mov     rcx, 861C46800h
0x140258a1e  imul    rax, rcx
0x140258a22  mov     r8d, dword ptr [rsp+0E8h+var_A8+4]
0x140258a27  shl     r8, 20h
0x140258a2b  sub     r8, rax
0x140258a2e  mov     eax, dword ptr [rsp+0E8h+var_A8]
0x140258a32  add     r8, rax
0x140258a35  mov     rax, 0D6BF94D5E57A42BDh
0x140258a3f  imul    r8
0x140258a42  add     rdx, r8
0x140258a45  sar     rdx, 17h
0x140258a49  mov     rax, rdx
0x140258a4c  shr     rax, 3Fh
0x140258a50  add     rdx, rax
0x140258a53  imul    rax, rdx, 989680h
0x140258a5a  sub     r8, rax
0x140258a5d  mov     rax, 2B6109100h
0x140258a67  add     rax, rdx
0x140258a6a  imul    rcx, rax, 989680h
0x140258a71  add     rcx, r8
0x140258a74  mov     [rsp+0E8h+var_58], rcx
0x140258a7c  mov     edi, 80070002h
0x140258a81  jmp     loc_140258B17
0x140258a86  mov     rcx, [rsp+0E8h+var_80]
0x140258a8b  mov     rax, [rcx]
0x140258a8e  mov     [rsp+0E8h+var_B8], r13d
0x140258a93  mov     [rsp+0E8h+var_C0], r13d
0x140258a98  lea     rdx, [rsp+0E8h+var_88]
0x140258a9d  mov     [rsp+0E8h+ppv], rdx; int
0x140258aa2  lea     r9, [rsp+0E8h+var_84]
0x140258aa7  lea     r8, [rsp+0E8h+var_70]
0x140258aac  lea     rdx, [rsp+0E8h+var_58]
0x140258ab4  mov     rax, [rax+58h]
0x140258ab8  call    _guard_dispatch_icall
0x140258abd  mov     edi, 80070002h
0x140258ac2  cmp     eax, edi
0x140258ac4  jnz     short loc_140258B02
0x140258ac6  lea     rax, aWaasAssessorRe; "Waas assessor returned file not found, "...
0x140258acd  mov     [rsp+0E8h+var_A8], rax
0x140258ad2  mov     [rsp+0E8h+var_A0], 3Ah ; ':'
0x140258adb  lea     rcx, [rsp+0E8h+var_A8]
0x140258ae0  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x140258ae5  nop
0x140258ae6  mov     rcx, [rsp+0E8h+var_80]
0x140258aeb  test    rcx, rcx
0x140258aee  jz      short loc_140258AFD
0x140258af0  mov     rax, [rcx]
0x140258af3  mov     rax, [rax+10h]
0x140258af7  call    _guard_dispatch_icall
0x140258afc  nop
0x140258afd  jmp     loc_140258EF0
0x140258b02  mov     rcx, [rsp+0E8h]; this
0x140258b0a  test    eax, eax
0x140258b0c  js      loc_140258F31
0x140258b12  cmp     eax, r13d
0x140258b15  jz      short loc_140258B5C
0x140258b17  cmp     dword ptr [rsp+0E8h+var_70], 9
0x140258b1c  jnz     short loc_140258B43
0x140258b1e  lea     rax, aOverrideOutOfD_0; "Override out of date value for quality "...
0x140258b25  mov     [rsp+0E8h+var_A8], rax
0x140258b2a  mov     [rsp+0E8h+var_A0], 5Bh ; '['
0x140258b33  lea     rcx, [rsp+0E8h+var_A8]
0x140258b38  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x140258b3d  mov     [rsi+11h], r12b
0x140258b41  jmp     short loc_140258B5C
0x140258b43  cmp     [rsp+0E8h+var_84], r12d
0x140258b48  jz      short loc_140258B5C
0x140258b4a  cmp     [rsp+0E8h+var_88], r12d
0x140258b4f  jnz     short loc_140258B5C
0x140258b51  cmp     dword ptr [rsp+0E8h+var_70+4], 3
0x140258b56  setz    al
0x140258b59  mov     [rsi+11h], al
0x140258b5c  mov     [rsp+0E8h+var_40], r12
0x140258b64  mov     [rsp+0E8h+var_84], r12d
0x140258b69  mov     [rsp+0E8h+var_88], r12d
0x140258b6e  xor     eax, eax
0x140258b70  mov     [rsp+0E8h+var_50], rax
0x140258b78  mov     [rsp+0E8h+var_48], eax
0x140258b7f  mov     rcx, [rsp+0E8h+var_80]
0x140258b84  mov     rax, [rcx]
0x140258b87  mov     [rsp+0E8h+var_B8], r13d
0x140258b8c  mov     [rsp+0E8h+var_C0], 2
0x140258b94  lea     rdx, [rsp+0E8h+var_88]
0x140258b99  mov     [rsp+0E8h+ppv], rdx; int
0x140258b9e  lea     r9, [rsp+0E8h+var_84]
0x140258ba3  lea     r8, [rsp+0E8h+var_50]
0x140258bab  lea     rdx, [rsp+0E8h+var_40]
0x140258bb3  mov     rax, [rax+58h]
0x140258bb7  call    _guard_dispatch_icall
0x140258bbc  cmp     eax, edi
0x140258bbe  jnz     short loc_140258BFC
0x140258bc0  lea     rax, aWaasAssessorRe; "Waas assessor returned file not found, "...
0x140258bc7  mov     [rsp+0E8h+var_A8], rax
0x140258bcc  mov     [rsp+0E8h+var_A0], 3Ah ; ':'
0x140258bd5  lea     rcx, [rsp+0E8h+var_A8]
0x140258bda  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x140258bdf  nop
0x140258be0  mov     rcx, [rsp+0E8h+var_80]
0x140258be5  test    rcx, rcx
0x140258be8  jz      short loc_140258BF7
0x140258bea  mov     rax, [rcx]
0x140258bed  mov     rax, [rax+10h]
0x140258bf1  call    _guard_dispatch_icall
0x140258bf6  nop
0x140258bf7  jmp     loc_140258EF0
0x140258bfc  mov     rcx, [rsp+0E8h]; this
0x140258c04  test    eax, eax
0x140258c06  js      loc_140258F45
0x140258c0c  cmp     eax, r13d
0x140258c0f  jz      short loc_140258C59
0x140258c11  cmp     dword ptr [rsp+0E8h+var_50], 9
0x140258c19  jnz     short loc_140258C40
0x140258c1b  lea     rax, aOverrideOutOfD; "Override out of date value for feature "...
0x140258c22  mov     [rsp+0E8h+var_A8], rax
0x140258c27  mov     [rsp+0E8h+var_A0], 5Bh ; '['
0x140258c30  lea     rcx, [rsp+0E8h+var_A8]
0x140258c35  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x140258c3a  mov     [rsi+10h], r12b
0x140258c3e  jmp     short loc_140258C59
0x140258c40  cmp     [rsp+0E8h+var_84], r12d
0x140258c45  jz      short loc_140258C59
0x140258c47  cmp     [rsp+0E8h+var_88], r12d
0x140258c4c  jnz     short loc_140258C59
0x140258c4e  cmp     dword ptr [rsp+0E8h+var_70+4], 3
0x140258c53  setz    al
0x140258c56  mov     [rsi+10h], al
0x140258c59  mov     [rsp+0E8h+var_38], r12
0x140258c61  mov     [rsp+0E8h+var_78], r12d
0x140258c66  mov     rcx, [rsp+0E8h+var_80]
0x140258c6b  mov     rax, [rcx]
0x140258c6e  mov     dword ptr [rsp+0E8h+ppv], r13d; int
0x140258c73  lea     r9, [rsp+0E8h+var_38]
0x140258c7b  lea     r8, [rsp+0E8h+var_78]
0x140258c80  lea     rdx, [rsp+0E8h+var_88]
0x140258c85  mov     rax, [rax+50h]
0x140258c89  call    _guard_dispatch_icall
0x140258c8e  cmp     eax, edi
  ... truncated ...
```
