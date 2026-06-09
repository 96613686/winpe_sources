# AppReadiness::User::ScorePackages(void)

- ea: `0x180009380`
- end: `0x1800097bb`
- name: `?ScorePackages@User@AppReadiness@@QEAAXXZ`
- size: `1083`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010afc`
- `0x18002b08c`

## callees

- `0x180002958`
- `0x1800041e0`
- `0x180008d7c`
- `0x180009290`
- `0x180009380`
- `0x180009d00`
- `0x180009d60`
- `0x18000b464`
- `0x18003e210`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009755`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009755`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009402`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009402`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000964c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000964c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000962d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000962d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800096c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800096c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009500`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009500`

## string_xrefs

- `0x1800094f2`: `Software\Microsoft\Windows\CurrentVersion\AppReadiness`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall AppReadiness::User::ScorePackages(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // r15
  __int64 v3; // r8
  char *Ptr; // rdi
  char *i; // r14
  __int64 v6; // rsi
  const wchar_t *v7; // rdx
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  void **v13; // rbx
  const wchar_t *v14; // rdx
  const wchar_t *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  unsigned int v20; // ebx
  int LastError; // eax
  const WCHAR *v22; // rdx
  int v23; // ecx
  _QWORD *v24; // r9
  RTL_SRWLOCK *v25; // r8
  unsigned int v26; // [rsp+30h] [rbp-89h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-81h] BYREF
  char v28[4]; // [rsp+40h] [rbp-79h] BYREF
  DWORD Type; // [rsp+44h] [rbp-75h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-71h] BYREF
  void **v31; // [rsp+50h] [rbp-69h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-61h] BYREF
  RTL_SRWLOCK *v33; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v34[3]; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v35[16]; // [rsp+80h] [rbp-39h] BYREF
  const wchar_t *v36; // [rsp+90h] [rbp-29h]
  int v37; // [rsp+98h] [rbp-21h]
  int v38; // [rsp+9Ch] [rbp-1Dh]
  const wchar_t *v39; // [rsp+A0h] [rbp-19h]
  int v40; // [rsp+A8h] [rbp-11h]
  int v41; // [rsp+ACh] [rbp-Dh]
  BYTE *v42; // [rsp+B0h] [rbp-9h]
  __int64 v43; // [rsp+B8h] [rbp-1h]

  if ( !LOBYTE(this[22].Ptr) )
  {
    (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 1))(this);
    v33 = this;
    Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(&v33);
    v34[0] = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
    v34[1] = 0;
    (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 2))(this);
    AppReadiness::User::UpdatePackageMetadata(this);
    v2 = this + 7;
    AcquireSRWLockExclusive(this + 7);
    v34[2] = this + 7;
    Ptr = (char *)this[15].Ptr;
    for ( i = (char *)this[16].Ptr; Ptr != i; Ptr += 16 )
    {
      v6 = *(_QWORD *)Ptr;
      v26 = 0;
      if ( (Microsoft_Windows_AppReadinessEnableBits & 0x800000) != 0 )
      {
        v7 = (const wchar_t *)(v6 + 40);
        if ( *(_QWORD *)(v6 + 64) > 7u )
          v7 = *(const wchar_t **)v7;
        v8 = (const wchar_t *)&v33[8];
        if ( v33[11].Ptr > (PVOID)7 )
          v8 = *(const wchar_t **)v8;
        if ( v8 )
        {
          v9 = -1;
          do
            ++v9;
          while ( v8[v9] );
          v10 = 2 * v9 + 2;
        }
        else
        {
          v10 = 10;
          v8 = L"NULL";
        }
        v36 = v8;
        v37 = v10;
        v38 = 0;
        if ( v7 )
        {
          v11 = -1;
          do
            ++v11;
          while ( v7[v11] );
          v12 = 2 * v11 + 2;
        }
        else
        {
          v12 = 10;
          v7 = L"NULL";
        }
        v39 = v7;
        v40 = v12;
        v41 = 0;
        McGenEventWrite_EventWriteTransfer(v8, PackageScore_Start, v3, 3, v35);
      }
      v31 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
      hKey = 0;
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\AppReadiness",
             0,
             1u,
             &hKey) )
      {
        goto LABEL_18;
      }
      *(_DWORD *)Data = 0;
      Type = 0;
      cbData = 4;
      v22 = (const WCHAR *)(*(_QWORD *)Ptr + 40LL);
      if ( *(_QWORD *)(*(_QWORD *)Ptr + 64LL) > 7u )
        v22 = *(const WCHAR **)v22;
      if ( RegQueryValueExW(hKey, v22, 0, &Type, Data, &cbData) || Type != 4 || cbData != 4 )
      {
LABEL_18:
        v13 = (void **)off_18007A6B0;
        do
        {
          if ( !((unsigned __int8 (__fastcall *)(char *, unsigned int *, RTL_SRWLOCK **, char *))*v13)(
                  v28,
                  &v26,
                  &v33,
                  Ptr) )
            break;
          ++v13;
        }
        while ( v13 != &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable' );
        if ( (Microsoft_Windows_AppReadinessEnableBits & 0x800000) != 0 )
        {
          v14 = (const wchar_t *)(*(_QWORD *)Ptr + 40LL);
          if ( *(_QWORD *)(*(_QWORD *)Ptr + 64LL) > 7u )
            v14 = *(const wchar_t **)v14;
          v15 = (const wchar_t *)&v33[8];
          if ( v33[11].Ptr > (PVOID)7 )
            v15 = *(const wchar_t **)v15;
          *(_DWORD *)Data = v26;
          if ( v15 )
          {
            v16 = -1;
            do
              ++v16;
            while ( v15[v16] );
            v17 = 2 * v16 + 2;
          }
          else
          {
            v17 = 10;
            v15 = L"NULL";
          }
          v36 = v15;
          v37 = v17;
          v38 = 0;
          if ( v14 )
          {
            v18 = -1;
            do
              ++v18;
            while ( v14[v18] );
            v19 = 2 * v18 + 2;
          }
          else
          {
            v19 = 10;
            v14 = L"NULL";
          }
          v39 = v14;
          v40 = v19;
          v41 = 0;
          v42 = Data;
          v43 = 4;
          McGenEventWrite_EventWriteTransfer(v15, PackageScore_Stop, v26, 4, v35);
        }
        v20 = v26;
        v31 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
        if ( hKey )
        {
          if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(&v31) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            RaiseException(LastError, 1u, 0, 0);
            __debugbreak();
          }
          hKey = 0;
        }
      }
      else
      {
        v20 = *(_DWORD *)Data;
        v26 = *(_DWORD *)Data;
        if ( (Microsoft_Windows_AppReadinessEnableBits & 0x800000) != 0 )
        {
          v24 = (_QWORD *)(*(_QWORD *)Ptr + 40LL);
          if ( *(_QWORD *)(*(_QWORD *)Ptr + 64LL) > 7u )
            v24 = (_QWORD *)*v24;
          v25 = v33 + 8;
          if ( v33[11].Ptr > (PVOID)7 )
            v25 = (RTL_SRWLOCK *)v25->Ptr;
          McTemplateU0zzq_EventWriteTransfer(v23, (unsigned int)PackageScore_Stop, (_DWORD)v25, (_DWORD)v24, Data[0]);
          v20 = v26;
        }
        v31 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v31);
      }
      *(_DWORD *)(v6 + 136) = v20;
    }
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    v34[0] = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v34);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  }
}

```

## disassembly

```asm
0x180009380  push    rbp
0x180009382  push    rbx
0x180009383  push    rsi
0x180009384  push    rdi
0x180009385  push    r12
0x180009387  push    r13
0x180009389  push    r14
0x18000938b  push    r15
0x18000938d  lea     rbp, [rsp-1Fh]
0x180009392  sub     rsp, 0D8h
0x180009399  mov     rax, cs:__security_cookie
0x1800093a0  xor     rax, rsp
0x1800093a3  mov     [rbp+57h+var_50], rax
0x1800093a7  mov     rbx, rcx
0x1800093aa  cmp     byte ptr [rcx+0B0h], 0
0x1800093b1  jnz     loc_180009772
0x1800093b7  mov     rax, [rcx]
0x1800093ba  mov     rax, [rax+8]
0x1800093be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093c3  nop
0x1800093c4  mov     [rbp+57h+var_B0], rbx
0x1800093c8  lea     rcx, [rbp+57h+var_B0]
0x1800093cc  call    ?InternalAddRef@?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(void)
0x1800093d1  lea     r13, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x1800093d8  mov     [rbp+57h+var_A8], r13
0x1800093dc  xor     r12d, r12d
0x1800093df  mov     [rbp+57h+var_A0], r12
0x1800093e3  mov     rax, [rbx]
0x1800093e6  mov     rcx, rbx
0x1800093e9  mov     rax, [rax+10h]
0x1800093ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093f2  nop
0x1800093f3  mov     rcx, rbx; this
0x1800093f6  call    ?UpdatePackageMetadata@User@AppReadiness@@QEAAXXZ; AppReadiness::User::UpdatePackageMetadata(void)
0x1800093fb  lea     r15, [rbx+38h]
0x1800093ff  mov     rcx, r15; SRWLock
0x180009402  call    cs:__imp_AcquireSRWLockExclusive
0x180009408  mov     [rbp+57h+var_98], r15
0x18000940c  mov     rdi, [rbx+78h]
0x180009410  mov     r14, [rbx+80h]
0x180009417  cmp     rdi, r14
0x18000941a  jz      loc_18000974D
0x180009420  mov     rsi, [rdi]
0x180009423  mov     [rsp+110h+var_E0], r12d
0x180009428  cmp     byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+2, 0
0x18000942f  jge     loc_1800094D8
0x180009435  lea     rdx, [rsi+28h]
0x180009439  cmp     qword ptr [rsi+40h], 7
0x18000943e  jbe     short loc_180009443
0x180009440  mov     rdx, [rdx]
0x180009443  mov     rcx, [rbp+57h+var_B0]
0x180009447  add     rcx, 40h ; '@'
0x18000944b  cmp     qword ptr [rcx+18h], 7
0x180009450  ja      loc_180009653
0x180009456  test    rcx, rcx
0x180009459  jz      loc_180009792
0x18000945f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009466  nop     word ptr [rax+rax+00000000h]
0x180009470  lea     rax, [rax+1]
0x180009474  cmp     word ptr [rcx+rax*2], 0
0x180009479  jnz     short loc_180009470
0x18000947b  lea     eax, ds:2[rax*2]
0x180009482  mov     [rbp+57h+var_80], rcx
0x180009486  mov     [rbp+57h+var_78], eax
0x180009489  mov     [rbp+57h+var_74], r12d
0x18000948d  test    rdx, rdx
0x180009490  jz      loc_1800097A3
0x180009496  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000949d  nop     dword ptr [rax]
0x1800094a0  lea     rax, [rax+1]
0x1800094a4  cmp     word ptr [rdx+rax*2], 0
0x1800094a9  jnz     short loc_1800094A0
0x1800094ab  lea     eax, ds:2[rax*2]
0x1800094b2  mov     [rbp+57h+var_70], rdx
0x1800094b6  mov     [rbp+57h+var_68], eax
0x1800094b9  mov     [rbp+57h+var_64], r12d
0x1800094bd  lea     rax, [rbp+57h+var_90]
0x1800094c1  mov     [rsp+110h+phkResult], rax
0x1800094c6  mov     r9d, 3
0x1800094cc  lea     rdx, PackageScore_Start
0x1800094d3  call    McGenEventWrite_EventWriteTransfer
0x1800094d8  mov     [rbp+57h+var_C0], r13
0x1800094dc  mov     [rbp+57h+hKey], r12
0x1800094e0  lea     rax, [rbp+57h+hKey]
0x1800094e4  mov     [rsp+110h+phkResult], rax; phkResult
0x1800094e9  mov     r9d, 1; samDesired
0x1800094ef  xor     r8d, r8d; ulOptions
0x1800094f2  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800094f9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009500  call    cs:__imp_RegOpenKeyExW
0x180009506  test    eax, eax
0x180009508  jz      loc_180009685
0x18000950e  lea     rbx, off_18007A6B0
0x180009515  lea     r12, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x18000951c  mov     r9, rdi
0x18000951f  lea     r8, [rbp+57h+var_B0]
0x180009523  lea     rdx, [rsp+110h+var_E0]
0x180009528  lea     rcx, [rbp+57h+var_D0]
0x18000952c  mov     rax, [rbx]
0x18000952f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009534  test    al, al
0x180009536  jz      short loc_180009541
0x180009538  add     rbx, 8
0x18000953c  cmp     rbx, r12
0x18000953f  jnz     short loc_18000951C
0x180009541  cmp     byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+2, 0
0x180009548  mov     r12d, 0
0x18000954e  jge     loc_180009609
0x180009554  mov     r8d, [rsp+110h+var_E0]
0x180009559  mov     rdx, [rdi]
0x18000955c  add     rdx, 28h ; '('
0x180009560  cmp     qword ptr [rdx+18h], 7
0x180009565  jbe     short loc_18000956A
0x180009567  mov     rdx, [rdx]
0x18000956a  mov     rcx, [rbp+57h+var_B0]
0x18000956e  add     rcx, 40h ; '@'
0x180009572  cmp     qword ptr [rcx+18h], 7
0x180009577  ja      loc_18000967D
0x18000957d  mov     dword ptr [rsp+110h+Data], r8d
0x180009582  test    rcx, rcx
0x180009585  jz      loc_18000966C
0x18000958b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009592  lea     rax, [rax+1]
0x180009596  cmp     [rcx+rax*2], r12w
0x18000959b  jnz     short loc_180009592
0x18000959d  lea     eax, ds:2[rax*2]
0x1800095a4  mov     [rbp+57h+var_80], rcx
0x1800095a8  mov     [rbp+57h+var_78], eax
0x1800095ab  mov     [rbp+57h+var_74], r12d
0x1800095af  test    rdx, rdx
0x1800095b2  jz      loc_18000965B
0x1800095b8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800095bf  nop
0x1800095c0  lea     rax, [rax+1]
0x1800095c4  cmp     [rdx+rax*2], r12w
0x1800095c9  jnz     short loc_1800095C0
0x1800095cb  lea     eax, ds:2[rax*2]
0x1800095d2  mov     [rbp+57h+var_70], rdx
0x1800095d6  mov     [rbp+57h+var_68], eax
0x1800095d9  mov     [rbp+57h+var_64], r12d
0x1800095dd  lea     rax, [rsp+110h+Data]
0x1800095e2  mov     [rbp+57h+var_60], rax
0x1800095e6  mov     [rbp+57h+var_58], 4
0x1800095ee  lea     rax, [rbp+57h+var_90]
0x1800095f2  mov     [rsp+110h+phkResult], rax
0x1800095f7  mov     r9d, 4
0x1800095fd  lea     rdx, PackageScore_Stop
0x180009604  call    McGenEventWrite_EventWriteTransfer
0x180009609  mov     ebx, [rsp+110h+var_E0]
0x18000960d  mov     [rbp+57h+var_C0], r13
0x180009611  cmp     [rbp+57h+hKey], 0
0x180009616  jz      loc_18000973A
0x18000961c  lea     rcx, [rbp+57h+var_C0]
0x180009620  call    ?InternalClose@?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(void)
0x180009625  test    al, al
0x180009627  jnz     loc_1800097B4
0x18000962d  call    cs:__imp_GetLastError
0x180009633  test    eax, eax
0x180009635  jle     short loc_18000963F
0x180009637  movzx   eax, ax
0x18000963a  or      eax, 80070000h
0x18000963f  xor     r9d, r9d; lpArguments
0x180009642  xor     r8d, r8d; nNumberOfArguments
0x180009645  mov     edx, 1; dwExceptionFlags
0x18000964a  mov     ecx, eax; dwExceptionCode
0x18000964c  call    cs:__imp_RaiseException
0x180009652  int     3; Trap to Debugger
0x180009653  mov     rcx, [rcx]
0x180009656  jmp     loc_180009456
0x18000965b  mov     eax, 0Ah
0x180009660  lea     rdx, aNull_0; "NULL"
0x180009667  jmp     loc_1800095D2
0x18000966c  mov     eax, 0Ah
0x180009671  lea     rcx, aNull_0; "NULL"
0x180009678  jmp     loc_1800095A4
0x18000967d  mov     rcx, [rcx]
0x180009680  jmp     loc_18000957D
0x180009685  mov     dword ptr [rsp+110h+Data], r12d
0x18000968a  mov     [rbp+57h+Type], r12d
0x18000968e  mov     [rbp+57h+cbData], 4
0x180009695  mov     rdx, [rdi]
0x180009698  add     rdx, 28h ; '('
0x18000969c  cmp     qword ptr [rdx+18h], 7
0x1800096a1  jbe     short loc_1800096A6
0x1800096a3  mov     rdx, [rdx]; lpValueName
0x1800096a6  lea     rax, [rbp+57h+cbData]
0x1800096aa  mov     [rsp+110h+lpcbData], rax; lpcbData
0x1800096af  lea     rax, [rsp+110h+Data]
0x1800096b4  mov     [rsp+110h+phkResult], rax; lpData
0x1800096b9  lea     r9, [rbp+57h+Type]; lpType
0x1800096bd  xor     r8d, r8d; lpReserved
0x1800096c0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800096c4  call    cs:__imp_RegQueryValueExW
0x1800096ca  test    eax, eax
0x1800096cc  jnz     loc_18000950E
0x1800096d2  cmp     [rbp+57h+Type], 4
0x1800096d6  jnz     loc_18000950E
0x1800096dc  cmp     [rbp+57h+cbData], 4
0x1800096e0  jnz     loc_18000950E
0x1800096e6  mov     ebx, dword ptr [rsp+110h+Data]
0x1800096ea  mov     [rsp+110h+var_E0], ebx
0x1800096ee  cmp     byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+2, al
0x1800096f4  jge     short loc_18000972D
0x1800096f6  mov     r9, [rdi]
0x1800096f9  add     r9, 28h ; '('
0x1800096fd  cmp     qword ptr [r9+18h], 7
0x180009702  jbe     short loc_180009707
0x180009704  mov     r9, [r9]
0x180009707  mov     r8, [rbp+57h+var_B0]
0x18000970b  add     r8, 40h ; '@'
0x18000970f  cmp     qword ptr [r8+18h], 7
0x180009714  jbe     short loc_180009719
0x180009716  mov     r8, [r8]
0x180009719  mov     dword ptr [rsp+110h+phkResult], ebx
0x18000971d  lea     rdx, PackageScore_Stop
0x180009724  call    McTemplateU0zzq_EventWriteTransfer
0x180009729  mov     ebx, [rsp+110h+var_E0]
0x18000972d  mov     [rbp+57h+var_C0], r13
0x180009731  lea     rcx, [rbp+57h+var_C0]
0x180009735  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18000973a  mov     [rsi+88h], ebx
0x180009740  add     rdi, 10h
0x180009744  cmp     rdi, r14
0x180009747  jnz     loc_180009420
0x18000974d  test    r15, r15
0x180009750  jz      short loc_18000975C
0x180009752  mov     rcx, r15; SRWLock
0x180009755  call    cs:__imp_ReleaseSRWLockExclusive
0x18000975b  nop
0x18000975c  mov     [rbp+57h+var_A8], r13
0x180009760  lea     rcx, [rbp+57h+var_A8]
0x180009764  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180009769  lea     rcx, [rbp+57h+var_B0]
0x18000976d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180009772  mov     rcx, [rbp+57h+var_50]
0x180009776  xor     rcx, rsp; StackCookie
0x180009779  call    __security_check_cookie
0x18000977e  add     rsp, 0D8h
0x180009785  pop     r15
0x180009787  pop     r14
0x180009789  pop     r13
0x18000978b  pop     r12
0x18000978d  pop     rdi
0x18000978e  pop     rsi
0x18000978f  pop     rbx
0x180009790  pop     rbp
0x180009791  retn
0x180009792  mov     eax, 0Ah
0x180009797  lea     rcx, aNull_0; "NULL"
0x18000979e  jmp     loc_180009482
0x1800097a3  mov     eax, 0Ah
0x1800097a8  lea     rdx, aNull_0; "NULL"
0x1800097af  jmp     loc_1800094B2
0x1800097b4  mov     [rbp+57h+hKey], r12
0x1800097b8  jmp     short loc_18000973A
```
