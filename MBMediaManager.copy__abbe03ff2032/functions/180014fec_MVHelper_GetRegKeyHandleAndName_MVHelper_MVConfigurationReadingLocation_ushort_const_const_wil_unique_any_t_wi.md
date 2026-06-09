# MVHelper::GetRegKeyHandleAndName(MVHelper::_MVConfigurationReadingLocation,ushort const * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,bool)

- ea: `0x180014fec`
- end: `0x180015226`
- name: `?GetRegKeyHandleAndName@MVHelper@@AEAAJW4_MVConfigurationReadingLocation@1@QEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@_N@Z`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180024e38`

## callees

- `0x18000bde0`
- `0x180014fec`
- `0x1800198fc`
- `0x18001991c`
- `0x18002cd20`
- `0x18002d934`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800151ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800151ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001504a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800151bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001504a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800151bd`
- `MobileNetworking!GetPersistentRegPath` at `0x18001506c`
- `MobileNetworking!GetPersistentRegPath` at `0x18001506c`

## string_xrefs

- `0x1800150cf`: `Asking for per-ICCID value but ICCID is not ready yet.`
- `0x1800150ec`: `\IMSISpecific`
- `0x1800150af`: `\IMSISpecific\Default`
- `0x180015113`: `Asking for per-IMSI value of IMSI is not ready yet.`

## pseudocode

```c
int __fastcall MVHelper::GetRegKeyHandleAndName(_WORD *a1, int a2, __int64 a3, HKEY *a4, char a5)
{
  HKEY v5; // r14
  int result; // eax
  bool v11; // sf
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  const wchar_t *v15; // rax
  HKEY v16; // rbx
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[512]; // [rsp+40h] [rbp-C0h] BYREF

  v5 = *a4;
  LODWORD(v17) = 512;
  if ( v5 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v18);
    RegCloseKey(v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v18);
  }
  *a4 = 0;
  result = GetPersistentRegPath(1, 0, &v17, Buffer);
  v11 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v11 = result < 0;
  }
  if ( !v11 )
  {
    v12 = a2 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 2;
        if ( v14 )
        {
          if ( v14 != 4 )
            return -2147024809;
          v15 = L"\\IMSISpecific\\Default";
          goto LABEL_21;
        }
        if ( *a1 )
        {
          swprintf_s(Buffer, 0x200u, L"%s%s\\%s", Buffer, L"\\ICCIDSpecific", a1, v17);
LABEL_22:
          if ( a5 )
            swprintf_s(Buffer, 0x200u, L"%s%s", Buffer, L"\\CellUX");
          if ( a3 )
            swprintf_s(Buffer, 0x200u, L"%s\\%s", Buffer, a3);
          v16 = *a4;
          if ( *a4 )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)v18);
            RegCloseKey(v16);
            wil::last_error_context::~last_error_context((wil::last_error_context *)v18);
          }
          *a4 = 0;
          result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, Buffer, 0, 0x20019u, a4);
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
          return result;
        }
        MBSettingUXLogging::Warn(
          "MVHelper::GetRegKeyHandleAndName",
          209,
          "Asking for per-ICCID value but ICCID is not ready yet.");
      }
      else
      {
        if ( a1[22] )
        {
          swprintf_s(Buffer, 0x200u, L"%s%s\\%s", Buffer, L"\\IMSISpecific", a1 + 22, v17);
          goto LABEL_22;
        }
        MBSettingUXLogging::Warn(
          "MVHelper::GetRegKeyHandleAndName",
          220,
          "Asking for per-IMSI value of IMSI is not ready yet.");
      }
      return -2147023728;
    }
    v15 = L"\\DeviceSpecific";
LABEL_21:
    swprintf_s(Buffer, 0x200u, L"%s%s", Buffer, v15);
    goto LABEL_22;
  }
  return result;
}

```

## disassembly

```asm
0x180014fec  mov     [rsp-8+arg_8], rbx
0x180014ff1  push    rbp
0x180014ff2  push    rsi
0x180014ff3  push    rdi
0x180014ff4  push    r12
0x180014ff6  push    r13
0x180014ff8  push    r14
0x180014ffa  push    r15
0x180014ffc  lea     rbp, [rsp-350h]
0x180015004  sub     rsp, 450h
0x18001500b  mov     rax, cs:__security_cookie
0x180015012  xor     rax, rsp
0x180015015  mov     [rbp+380h+var_40], rax
0x18001501c  mov     r14, [r9]
0x18001501f  xor     r12d, r12d
0x180015022  mov     r13d, 200h
0x180015028  mov     rsi, r9
0x18001502b  mov     dword ptr [rsp+480h+var_450], r13d
0x180015030  mov     r15, r8
0x180015033  mov     ebx, edx
0x180015035  mov     rdi, rcx
0x180015038  test    r14, r14
0x18001503b  jz      short loc_18001505A
0x18001503d  lea     rcx, [rsp+480h+var_448]; this
0x180015042  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180015047  mov     rcx, r14; hKey
0x18001504a  call    cs:__imp_RegCloseKey
0x180015050  lea     rcx, [rsp+480h+var_448]; this
0x180015055  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001505a  xor     edx, edx
0x18001505c  mov     [rsi], r12
0x18001505f  lea     r9, [rsp+480h+Buffer]
0x180015064  lea     r8, [rsp+480h+var_450]
0x180015069  lea     ecx, [rdx+1]
0x18001506c  call    cs:__imp_GetPersistentRegPath
0x180015072  test    eax, eax
0x180015074  jle     short loc_180015080
0x180015076  movzx   eax, ax
0x180015079  or      eax, 80070000h
0x18001507e  test    eax, eax
0x180015080  js      loc_1800151FC
0x180015086  lea     r14, aSS_0; "%s%s"
0x18001508d  sub     ebx, 1
0x180015090  jz      loc_18001513A
0x180015096  sub     ebx, 1
0x180015099  jz      short loc_1800150DD
0x18001509b  sub     ebx, 2
0x18001509e  jz      short loc_1800150BB
0x1800150a0  cmp     ebx, 4
0x1800150a3  jz      short loc_1800150AF
0x1800150a5  mov     eax, 80070057h
0x1800150aa  jmp     loc_1800151FC
0x1800150af  lea     rax, aImsispecificDe; "\\IMSISpecific\\Default"
0x1800150b6  jmp     loc_180015141
0x1800150bb  cmp     [rdi], r12w
0x1800150bf  jz      short loc_1800150CF
0x1800150c1  mov     [rsp+480h+var_458], rdi
0x1800150c6  lea     rax, aIccidspecific; "\\ICCIDSpecific"
0x1800150cd  jmp     short loc_1800150F3
0x1800150cf  lea     r8, aAskingForPerIc; "Asking for per-ICCID value but ICCID is"...
0x1800150d6  mov     edx, 0D1h
0x1800150db  jmp     short loc_18001511F
0x1800150dd  lea     rax, [rdi+2Ch]
0x1800150e1  cmp     [rax], r12w
0x1800150e5  jz      short loc_180015113
0x1800150e7  mov     [rsp+480h+var_458], rax
0x1800150ec  lea     rax, aImsispecific; "\\IMSISpecific"
0x1800150f3  lea     r9, [rsp+480h+Buffer]
0x1800150f8  mov     [rsp+480h+phkResult], rax
0x1800150fd  lea     r8, aSSS; "%s%s\\%s"
0x180015104  mov     rdx, r13; BufferCount
0x180015107  lea     rcx, [rsp+480h+Buffer]; Buffer
0x18001510c  call    swprintf_s
0x180015111  jmp     short loc_18001515B
0x180015113  lea     r8, aAskingForPerIm; "Asking for per-IMSI value of IMSI is no"...
0x18001511a  mov     edx, 0DCh; unsigned int
0x18001511f  lea     rcx, aMvhelperGetreg; "MVHelper::GetRegKeyHandleAndName"
0x180015126  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x18001512b  mov     eax, 80070490h
0x180015130  test    eax, eax
0x180015132  js      loc_1800151FC
0x180015138  jmp     short loc_18001515B
0x18001513a  lea     rax, aDevicespecific; "\\DeviceSpecific"
0x180015141  lea     r9, [rsp+480h+Buffer]
0x180015146  mov     [rsp+480h+phkResult], rax
0x18001514b  mov     r8, r14; Format
0x18001514e  lea     rcx, [rsp+480h+Buffer]; Buffer
0x180015153  mov     rdx, r13; BufferCount
0x180015156  call    swprintf_s
0x18001515b  cmp     [rbp+380h+arg_20], r12b
0x180015162  jz      short loc_180015185
0x180015164  lea     rax, aCellux_0; "\\CellUX"
0x18001516b  mov     r8, r14; Format
0x18001516e  lea     r9, [rsp+480h+Buffer]
0x180015173  mov     [rsp+480h+phkResult], rax
0x180015178  mov     rdx, r13; BufferCount
0x18001517b  lea     rcx, [rsp+480h+Buffer]; Buffer
0x180015180  call    swprintf_s
0x180015185  test    r15, r15
0x180015188  jz      short loc_1800151A8
0x18001518a  lea     r9, [rsp+480h+Buffer]
0x18001518f  mov     [rsp+480h+phkResult], r15
0x180015194  lea     r8, aSS; "%s\\%s"
0x18001519b  mov     rdx, r13; BufferCount
0x18001519e  lea     rcx, [rsp+480h+Buffer]; Buffer
0x1800151a3  call    swprintf_s
0x1800151a8  mov     rbx, [rsi]
0x1800151ab  test    rbx, rbx
0x1800151ae  jz      short loc_1800151CD
0x1800151b0  lea     rcx, [rsp+480h+var_448]; this
0x1800151b5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800151ba  mov     rcx, rbx; hKey
0x1800151bd  call    cs:__imp_RegCloseKey
0x1800151c3  lea     rcx, [rsp+480h+var_448]; this
0x1800151c8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800151cd  mov     r9d, 20019h; samDesired
0x1800151d3  mov     [rsi], r12
0x1800151d6  xor     r8d, r8d; ulOptions
0x1800151d9  mov     [rsp+480h+phkResult], rsi; phkResult
0x1800151de  lea     rdx, [rsp+480h+Buffer]; lpSubKey
0x1800151e3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800151ea  call    cs:__imp_RegOpenKeyExW
0x1800151f0  test    eax, eax
0x1800151f2  jle     short loc_1800151FC
0x1800151f4  movzx   eax, ax
0x1800151f7  or      eax, 80070000h
0x1800151fc  mov     rcx, [rbp+380h+var_40]
0x180015203  xor     rcx, rsp; StackCookie
0x180015206  call    __security_check_cookie
0x18001520b  mov     rbx, [rsp+480h+arg_8]
0x180015213  add     rsp, 450h
0x18001521a  pop     r15
0x18001521c  pop     r14
0x18001521e  pop     r13
0x180015220  pop     r12
0x180015222  pop     rdi
0x180015223  pop     rsi
0x180015224  pop     rbp
0x180015225  retn
```
