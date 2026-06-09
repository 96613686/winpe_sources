# MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)

- ea: `0x180014490`
- end: `0x1800147ff`
- name: `?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z`
- size: `879`
- prototype: `__int64 __fastcall(MVHelper *this, const WCHAR *, int, __int64, const unsigned __int16 *, BYTE *lpData)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18000b500`
- `0x18004c768`

## callees

- `0x18000ad20`
- `0x18000bde0`
- `0x180014490`
- `0x1800198fc`
- `0x18001991c`
- `0x18002cd20`
- `0x18002d934`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001467f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001467f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014700`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014700`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800146ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001478f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800147ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800146ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001478f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800147ea`
- `MobileNetworking!GetPersistentRegPath` at `0x18001457d`
- `MobileNetworking!GetPersistentRegPath` at `0x18001457d`

## string_xrefs

- `0x180014509`: `GetStringValue Succeeded. readLocation=%d, wszName=%ls, wstrValue=%ls`
- `0x1800146bc`: `GetStringValue Error. wszName=%ls, dwReadingRule=%d, HRESULT=0x%x`
- `0x1800145ed`: `Asking for per-ICCID value but ICCID is not ready yet.`
- `0x1800147c0`: `\IMSISpecific`
- `0x1800147a9`: `\IMSISpecific\Default`
- `0x1800147cc`: `Asking for per-IMSI value of IMSI is not ready yet.`

## pseudocode

```c
__int64 __fastcall MVHelper::GetStringValue(
        MVHelper *this,
        const WCHAR *a2,
        int a3,
        __int64 a4,
        const unsigned __int16 *a5,
        BYTE *lpData)
{
  char v7; // r15
  signed int v10; // ebx
  int v11; // edi
  int PersistentRegPath; // eax
  HKEY v14; // rbx
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  const wchar_t *v17; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v22; // [rsp+48h] [rbp-B8h]
  _BYTE v23[16]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Buffer[512]; // [rsp+60h] [rbp-A0h] BYREF

  v7 = 0;
  v22 = a5;
  v10 = -2147023728;
  while ( 1 )
  {
    v11 = a3 & (15 << (4 * v7));
    if ( !v11 )
    {
      MBSettingUXLogging::Warn(
        "MVHelper::GetStringValue",
        0xB2u,
        "GetStringValue Error. wszName=%ls, dwReadingRule=%d, HRESULT=0x%x",
        a2,
        a3,
        v10);
      return (unsigned int)v10;
    }
    Type = 0;
    hKey = 0;
    cbData = 512;
    v20 = 512;
    PersistentRegPath = GetPersistentRegPath(1, 0, &v20, Buffer);
    v10 = PersistentRegPath;
    if ( PersistentRegPath > 0 )
      v10 = (unsigned __int16)PersistentRegPath | 0x80070000;
    if ( v10 >= 0 )
      break;
LABEL_23:
    ++v7;
    if ( hKey )
      RegCloseKey(hKey);
  }
  if ( v11 == 1 )
  {
    v17 = L"\\DeviceSpecific";
LABEL_31:
    swprintf_s(Buffer, 0x200u, L"%s%s", Buffer, v17);
    goto LABEL_16;
  }
  if ( v11 != 2 )
  {
    if ( v11 == 4 )
    {
      if ( *(_WORD *)this )
      {
        swprintf_s(Buffer, 0x200u, L"%s%s\\%s", Buffer, L"\\ICCIDSpecific", this);
        goto LABEL_16;
      }
      MBSettingUXLogging::Warn(
        "MVHelper::GetRegKeyHandleAndName",
        0xD1u,
        "Asking for per-ICCID value but ICCID is not ready yet.");
LABEL_15:
      v10 = -2147023728;
      goto LABEL_23;
    }
    if ( v11 != 8 )
    {
      v10 = -2147024809;
      goto LABEL_23;
    }
    v17 = L"\\IMSISpecific\\Default";
    goto LABEL_31;
  }
  if ( !*((_WORD *)this + 22) )
  {
    MBSettingUXLogging::Warn(
      "MVHelper::GetRegKeyHandleAndName",
      0xDCu,
      "Asking for per-IMSI value of IMSI is not ready yet.");
    goto LABEL_15;
  }
  swprintf_s(Buffer, 0x200u, L"%s%s\\%s", Buffer, L"\\IMSISpecific", (char *)this + 44);
LABEL_16:
  swprintf_s(Buffer, 0x200u, L"%s%s", Buffer, L"\\CellUX");
  if ( v22 )
    swprintf_s(Buffer, 0x200u, L"%s\\%s", Buffer, v22);
  v14 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v23);
    RegCloseKey(v14);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v23);
  }
  hKey = 0;
  v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, Buffer, 0, 0x20019u, &hKey);
  v10 = v15;
  if ( v15 > 0 )
    v10 = (unsigned __int16)v15 | 0x80070000;
  if ( v10 < 0 )
    goto LABEL_23;
  v16 = RegQueryValueExW(hKey, a2, 0, &Type, lpData, &cbData);
  v10 = v16;
  if ( v16 > 0 )
    v10 = (unsigned __int16)v16 | 0x80070000;
  if ( v10 < 0 )
    goto LABEL_23;
  if ( Type != 1 )
  {
    v10 = -2147418113;
    goto LABEL_23;
  }
  if ( hKey )
    RegCloseKey(hKey);
  MBSettingUXLogging::Info(
    "MVHelper::GetStringValue",
    0xAEu,
    "GetStringValue Succeeded. readLocation=%d, wszName=%ls, wstrValue=%ls",
    v11,
    a2,
    (const wchar_t *)lpData);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180014490  mov     [rsp-8+arg_18], rbx
0x180014495  push    rbp
0x180014496  push    rsi
0x180014497  push    rdi
0x180014498  push    r12
0x18001449a  push    r13
0x18001449c  push    r14
0x18001449e  push    r15
0x1800144a0  lea     rbp, [rsp-370h]
0x1800144a8  sub     rsp, 470h
0x1800144af  mov     rax, cs:__security_cookie
0x1800144b6  xor     rax, rsp
0x1800144b9  mov     [rbp+3A0h+var_40], rax
0x1800144c0  mov     rax, [rbp+3A0h+arg_20]
0x1800144c7  mov     rsi, rdx
0x1800144ca  mov     r13, [rbp+3A0h+lpData]
0x1800144d1  xor     edx, edx
0x1800144d3  mov     r15d, edx
0x1800144d6  mov     [rsp+4A0h+var_458], rax
0x1800144db  mov     r12d, r8d
0x1800144de  mov     r14, rcx
0x1800144e1  mov     ebx, 80070490h
0x1800144e6  lea     ecx, ds:0[r15*4]
0x1800144ee  mov     edi, 0Fh
0x1800144f3  shl     edi, cl
0x1800144f5  and     edi, r12d
0x1800144f8  jnz     short loc_180014555
0x1800144fa  test    ebx, ebx
0x1800144fc  js      loc_1800146B8
0x180014502  mov     edi, edx
0x180014504  mov     [rsp+4A0h+lpcbData], r13
0x180014509  lea     r8, aGetstringvalue; "GetStringValue Succeeded. readLocation="...
0x180014510  mov     r9d, edi
0x180014513  mov     [rsp+4A0h+phkResult], rsi
0x180014518  mov     edx, 0AEh; unsigned int
0x18001451d  lea     rcx, aMvhelperGetstr; "MVHelper::GetStringValue"
0x180014524  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180014529  mov     eax, ebx
0x18001452b  mov     rcx, [rbp+3A0h+var_40]
0x180014532  xor     rcx, rsp; StackCookie
0x180014535  call    __security_check_cookie
0x18001453a  mov     rbx, [rsp+4A0h+arg_18]
0x180014542  add     rsp, 470h
0x180014549  pop     r15
0x18001454b  pop     r14
0x18001454d  pop     r13
0x18001454f  pop     r12
0x180014551  pop     rdi
0x180014552  pop     rsi
0x180014553  pop     rbp
0x180014554  retn
0x180014555  mov     [rsp+4A0h+Type], edx
0x180014559  lea     r9, [rsp+4A0h+Buffer]
0x18001455e  mov     [rsp+4A0h+hKey], rdx
0x180014563  lea     r8, [rsp+4A0h+var_464]
0x180014568  xor     edx, edx
0x18001456a  mov     [rsp+4A0h+cbData], 200h
0x180014572  mov     [rsp+4A0h+var_464], 200h
0x18001457a  lea     ecx, [rdx+1]
0x18001457d  call    cs:__imp_GetPersistentRegPath
0x180014583  xor     edx, edx
0x180014585  mov     ebx, eax
0x180014587  test    eax, eax
0x180014589  jle     short loc_180014594
0x18001458b  movzx   ebx, ax
0x18001458e  or      ebx, 80070000h
0x180014594  test    ebx, ebx
0x180014596  js      loc_18001469A
0x18001459c  mov     ecx, edi
0x18001459e  sub     ecx, 1
0x1800145a1  jz      loc_180014755
0x1800145a7  sub     ecx, 1
0x1800145aa  jz      loc_1800147B2
0x1800145b0  sub     ecx, 2
0x1800145b3  jnz     loc_18001479A
0x1800145b9  cmp     [r14], dx
0x1800145bd  jz      short loc_1800145ED
0x1800145bf  mov     [rsp+4A0h+lpcbData], r14
0x1800145c4  lea     rax, aIccidspecific; "\\ICCIDSpecific"
0x1800145cb  lea     r9, [rsp+4A0h+Buffer]
0x1800145d0  mov     [rsp+4A0h+phkResult], rax
0x1800145d5  lea     r8, aSSS; "%s%s\\%s"
0x1800145dc  mov     edx, 200h; BufferCount
0x1800145e1  lea     rcx, [rsp+4A0h+Buffer]; Buffer
0x1800145e6  call    swprintf_s
0x1800145eb  jmp     short loc_180014614
0x1800145ed  lea     r8, aAskingForPerIc; "Asking for per-ICCID value but ICCID is"...
0x1800145f4  mov     edx, 0D1h; unsigned int
0x1800145f9  lea     rcx, aMvhelperGetreg; "MVHelper::GetRegKeyHandleAndName"
0x180014600  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x180014605  xor     edx, edx
0x180014607  mov     ebx, 80070490h
0x18001460c  test    ebx, ebx
0x18001460e  js      loc_18001469A
0x180014614  lea     rax, aCellux_0; "\\CellUX"
0x18001461b  mov     edx, 200h; BufferCount
0x180014620  lea     r9, [rsp+4A0h+Buffer]
0x180014625  mov     [rsp+4A0h+phkResult], rax
0x18001462a  lea     r8, aSS_0; "%s%s"
0x180014631  lea     rcx, [rsp+4A0h+Buffer]; Buffer
0x180014636  call    swprintf_s
0x18001463b  mov     rax, [rsp+4A0h+var_458]
0x180014640  test    rax, rax
0x180014643  jnz     loc_180014730
0x180014649  mov     rbx, [rsp+4A0h+hKey]
0x18001464e  test    rbx, rbx
0x180014651  jnz     loc_1800147DD
0x180014657  lea     rax, [rsp+4A0h+hKey]
0x18001465c  mov     [rsp+4A0h+hKey], 0
0x180014665  mov     r9d, 20019h; samDesired
0x18001466b  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180014670  xor     r8d, r8d; ulOptions
0x180014673  lea     rdx, [rsp+4A0h+Buffer]; lpSubKey
0x180014678  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001467f  call    cs:__imp_RegOpenKeyExW
0x180014685  xor     edx, edx
0x180014687  mov     ebx, eax
0x180014689  test    eax, eax
0x18001468b  jle     short loc_180014696
0x18001468d  movzx   ebx, ax
0x180014690  or      ebx, 80070000h
0x180014696  test    ebx, ebx
0x180014698  jns     short loc_1800146E1
0x18001469a  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18001469f  inc     r15d
0x1800146a2  test    rcx, rcx
0x1800146a5  jz      loc_1800144E6
0x1800146ab  call    cs:__imp_RegCloseKey
0x1800146b1  xor     edx, edx
0x1800146b3  jmp     loc_1800144E6
0x1800146b8  mov     dword ptr [rsp+4A0h+lpcbData], ebx
0x1800146bc  lea     r8, aGetstringvalue_0; "GetStringValue Error. wszName=%ls, dwRe"...
0x1800146c3  mov     r9, rsi
0x1800146c6  mov     dword ptr [rsp+4A0h+phkResult], r12d
0x1800146cb  mov     edx, 0B2h; unsigned int
0x1800146d0  lea     rcx, aMvhelperGetstr; "MVHelper::GetStringValue"
0x1800146d7  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x1800146dc  jmp     loc_180014529
0x1800146e1  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800146e6  lea     rax, [rsp+4A0h+cbData]
0x1800146eb  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x1800146f0  lea     r9, [rsp+4A0h+Type]; lpType
0x1800146f5  xor     r8d, r8d; lpReserved
0x1800146f8  mov     [rsp+4A0h+phkResult], r13; lpData
0x1800146fd  mov     rdx, rsi; lpValueName
0x180014700  call    cs:__imp_RegQueryValueExW
0x180014706  xor     edx, edx
0x180014708  mov     ebx, eax
0x18001470a  test    eax, eax
0x18001470c  jle     short loc_180014717
0x18001470e  movzx   ebx, ax
0x180014711  or      ebx, 80070000h
0x180014717  test    ebx, ebx
0x180014719  js      loc_18001469A
0x18001471f  cmp     [rsp+4A0h+Type], 1
0x180014724  jz      short loc_180014781
0x180014726  mov     ebx, 8000FFFFh
0x18001472b  jmp     loc_18001469A
0x180014730  lea     r9, [rsp+4A0h+Buffer]
0x180014735  mov     [rsp+4A0h+phkResult], rax
0x18001473a  lea     r8, aSS; "%s\\%s"
0x180014741  mov     edx, 200h; BufferCount
0x180014746  lea     rcx, [rsp+4A0h+Buffer]; Buffer
0x18001474b  call    swprintf_s
0x180014750  jmp     loc_180014649
0x180014755  lea     rax, aDevicespecific; "\\DeviceSpecific"
0x18001475c  lea     r9, [rsp+4A0h+Buffer]
0x180014761  mov     [rsp+4A0h+phkResult], rax
0x180014766  lea     r8, aSS_0; "%s%s"
0x18001476d  mov     edx, 200h; BufferCount
0x180014772  lea     rcx, [rsp+4A0h+Buffer]; Buffer
0x180014777  call    swprintf_s
0x18001477c  jmp     loc_180014614
0x180014781  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180014786  test    rcx, rcx
0x180014789  jz      loc_180014504
0x18001478f  call    cs:__imp_RegCloseKey
0x180014795  jmp     loc_180014504
0x18001479a  cmp     ecx, 4
0x18001479d  jz      short loc_1800147A9
0x18001479f  mov     ebx, 80070057h
0x1800147a4  jmp     loc_18001469A
0x1800147a9  lea     rax, aImsispecificDe; "\\IMSISpecific\\Default"
0x1800147b0  jmp     short loc_18001475C
0x1800147b2  lea     rax, [r14+2Ch]
0x1800147b6  cmp     [rax], dx
0x1800147b9  jz      short loc_1800147CC
0x1800147bb  mov     [rsp+4A0h+lpcbData], rax
0x1800147c0  lea     rax, aImsispecific; "\\IMSISpecific"
0x1800147c7  jmp     loc_1800145CB
0x1800147cc  lea     r8, aAskingForPerIm; "Asking for per-IMSI value of IMSI is no"...
0x1800147d3  mov     edx, 0DCh
0x1800147d8  jmp     loc_1800145F9
0x1800147dd  lea     rcx, [rsp+4A0h+var_450]; this
0x1800147e2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800147e7  mov     rcx, rbx; hKey
0x1800147ea  call    cs:__imp_RegCloseKey
0x1800147f0  lea     rcx, [rsp+4A0h+var_450]; this
0x1800147f5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800147fa  jmp     loc_180014657
```
