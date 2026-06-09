# Windows::Rtl::AutoHive::Load(ulong,_LUNICODE_STRING const &,_LUNICODE_STRING const &,ulong *)

- ea: `0x1800df5a8`
- end: `0x1800df92d`
- name: `?Load@AutoHive@Rtl@Windows@@QEAAJKAEBU_LUNICODE_STRING@@0PEAK@Z`
- size: `901`
- prototype: `__int64 __fastcall(Windows::Rtl::AutoHive *__hidden this, unsigned int, const struct _LUNICODE_STRING *, const struct _LUNICODE_STRING *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800df934`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x180048f3c`
- `0x1800497c0`
- `0x18004d970`
- `0x18004e028`
- `0x18004e0d4`
- `0x1800decc8`
- `0x1800dede8`
- `0x1800df5a8`
- `0x1801a18f4`

## import_xrefs

- `ntdll!NtLoadKey2` at `0x1800df772`
- `ntdll!NtLoadKey2` at `0x1800df794`
- `ntdll!NtLoadKey2` at `0x1800df772`
- `ntdll!NtLoadKey2` at `0x1800df794`
- `ntdll!NtOpenKeyEx` at `0x1800df74e`
- `ntdll!NtOpenKeyEx` at `0x1800df802`
- `ntdll!NtOpenKeyEx` at `0x1800df74e`
- `ntdll!NtOpenKeyEx` at `0x1800df802`

## string_xrefs

- `0x1800df835`: `NtOpenKeyEx(&m_RootKey, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))), &RootKeyAttributes, (0x00000004L))`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Rtl::AutoHive::Load(
        Windows::Rtl::AutoHive *this,
        __int64 a2,
        const struct _LUNICODE_STRING *a3,
        const struct _LUNICODE_STRING *a4)
{
  __int64 result; // rax
  NTSTATUS v7; // ebx
  int v8; // esi
  const char *v9; // rax
  unsigned __int16 i; // cx
  __int128 v11; // xmm1
  const char *v12; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+30h] [rbp-D8h]
  __int64 v14; // [rsp+38h] [rbp-D0h]
  const char *v15; // [rsp+40h] [rbp-C8h]
  __int64 v16; // [rsp+48h] [rbp-C0h]
  struct _OBJECT_ATTRIBUTES FileObjectAttributes; // [rsp+50h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES KeyObjectAttributes; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v19[4]; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v20; // [rsp+D0h] [rbp-38h]
  __int128 v21; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-10h] BYREF
  char v23; // [rsp+100h] [rbp-8h]
  __int128 v24; // [rsp+108h] [rbp+0h] BYREF
  __int128 v25; // [rsp+118h] [rbp+10h] BYREF

  v16 = -2;
  v24 = 0;
  result = RtlInitUnicodeStringFromLUnicodeString(a3, &v24);
  if ( (int)result < 0 )
    return result;
  v25 = 0;
  result = RtlInitUnicodeStringFromLUnicodeString(a4, &v25);
  if ( (int)result < 0 )
    return result;
  v21 = 0;
  v12 = (const char *)&v21;
  v7 = Windows::StringUtil::Rtl::DuplicateString<_UNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(
         &v24,
         &v12);
  if ( v7 < 0 )
    goto LABEL_4;
  v12 = (const char *)&v21;
  v7 = Windows::StringUtil::Rtl::EnsureTrailingNtPathSlash<Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(&v12);
  if ( v7 < 0 )
    goto LABEL_4;
  *(_QWORD *)&KeyObjectAttributes.Length = 48;
  KeyObjectAttributes.RootDirectory = 0;
  KeyObjectAttributes.ObjectName = (PUNICODE_STRING)&v24;
  *(_QWORD *)&KeyObjectAttributes.Attributes = 64;
  *(_OWORD *)&KeyObjectAttributes.SecurityDescriptor = 0;
  v19[0] = 48;
  v19[1] = 0;
  v19[2] = &v21;
  v19[3] = 64;
  v20 = 0;
  *(_QWORD *)&FileObjectAttributes.Length = 48;
  FileObjectAttributes.RootDirectory = 0;
  FileObjectAttributes.ObjectName = (PUNICODE_STRING)&v25;
  *(_QWORD *)&FileObjectAttributes.Attributes = 64;
  *(_OWORD *)&FileObjectAttributes.SecurityDescriptor = 0;
  v22 = 0;
  v23 = 0;
  if ( *(_QWORD *)this )
  {
LABEL_36:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1800DF92CLL);
  }
  v12 = (const char *)&RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs;
  v13 = 3;
  v7 = RtlSystemUtil::PrivilegeAcquisition::Acquire(&v22, &v12);
  if ( v7 < 0 )
  {
LABEL_11:
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v22);
LABEL_4:
    if ( *((_QWORD *)&v21 + 1) )
      anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)&v21 + 1));
    return (unsigned int)v7;
  }
  v7 = 0;
  v8 = 0;
  while ( 1 )
  {
    if ( (int)NtOpenKeyEx(this, 131097, v19, 4) >= 0 )
    {
      if ( v7 >= 0 )
        goto LABEL_26;
LABEL_35:
      v12 = "OneCore\\internal\\Base\\inc\\auto_hive.h";
      v13 = (__int64)"Windows::Rtl::AutoHive::Load";
      v14 = 242;
      v9 = "Status";
LABEL_23:
      v15 = v9;
LABEL_24:
      RtlReportErrorOrigination(&v12, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v7);
      goto LABEL_11;
    }
    v7 = NtLoadKey2(&KeyObjectAttributes, &FileObjectAttributes, 0x2000u);
    if ( v7 == -1073741583 )
      v7 = NtLoadKey2(&KeyObjectAttributes, &FileObjectAttributes, 0);
    if ( v7 >= 0 )
      break;
    if ( v7 != -1073741757 )
    {
      v12 = "OneCore\\internal\\Base\\inc\\auto_hive.h";
      v13 = (__int64)"Windows::Rtl::AutoHive::Load";
      v14 = 228;
      v15 = 0;
      goto LABEL_24;
    }
    DelayExecution(200);
    if ( ++v8 > 20 )
      goto LABEL_35;
  }
  v7 = NtOpenKeyEx(this, 131097, v19, 4);
  if ( v7 < 0 )
  {
    v12 = "OneCore\\internal\\Base\\inc\\auto_hive.h";
    v13 = (__int64)"Windows::Rtl::AutoHive::Load";
    v14 = 174;
    v9 = "NtOpenKeyEx(&m_RootKey, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))), &RootKeyAttrib"
         "utes, (0x00000004L))";
    goto LABEL_23;
  }
  *((_BYTE *)this + 40) = 1;
LABEL_26:
  for ( i = v21; i >= 2u; LOWORD(v21) = i )
  {
    if ( *(_WORD *)(*((_QWORD *)&v21 + 1) + 2 * ((unsigned __int64)i >> 1) - 2) != 92 )
      break;
    if ( !i )
      goto LABEL_36;
    i -= 2;
  }
  v11 = *(_OWORD *)((char *)this + 8);
  *(_OWORD *)((char *)this + 8) = v21;
  v21 = v11;
  *((_DWORD *)this + 11) = 2;
  v12 = (char *)this + 24;
  v7 = Windows::StringUtil::Rtl::DuplicateString<_UNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(
         &v25,
         &v12);
  if ( v7 < 0 )
    goto LABEL_11;
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v22);
  if ( *((_QWORD *)&v21 + 1) )
    anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)&v21 + 1));
  return 0;
}

```

## disassembly

```asm
0x1800df5a8  mov     rax, rsp
0x1800df5ab  push    rbp
0x1800df5ac  push    rdi
0x1800df5ad  push    r14
0x1800df5af  lea     rbp, [rax-48h]
0x1800df5b3  sub     rsp, 130h
0x1800df5ba  mov     [rsp+140h+var_100], 0FFFFFFFFFFFFFFFEh
0x1800df5c3  mov     [rax+10h], rbx
0x1800df5c7  mov     [rax+18h], rsi
0x1800df5cb  mov     rax, cs:__security_cookie
0x1800df5d2  xor     rax, rsp
0x1800df5d5  mov     [rbp+40h+var_20], rax
0x1800df5d9  mov     rbx, r9
0x1800df5dc  mov     rdi, rcx
0x1800df5df  xorps   xmm0, xmm0
0x1800df5e2  movups  [rbp+40h+var_40], xmm0
0x1800df5e6  lea     rdx, [rbp+40h+var_40]
0x1800df5ea  mov     rcx, r8
0x1800df5ed  call    RtlInitUnicodeStringFromLUnicodeString
0x1800df5f2  xor     r14d, r14d
0x1800df5f5  test    eax, eax
0x1800df5f7  js      short loc_1800DF644
0x1800df5f9  xorps   xmm0, xmm0
0x1800df5fc  movups  [rbp+40h+var_30], xmm0
0x1800df600  lea     rdx, [rbp+40h+var_30]
0x1800df604  mov     rcx, rbx
0x1800df607  call    RtlInitUnicodeStringFromLUnicodeString
0x1800df60c  test    eax, eax
0x1800df60e  js      short loc_1800DF644
0x1800df610  xorps   xmm0, xmm0
0x1800df613  movups  [rbp+40h+var_60], xmm0
0x1800df617  lea     rax, [rbp+40h+var_60]
0x1800df61b  mov     [rsp+140h+var_120], rax
0x1800df620  lea     rdx, [rsp+140h+var_120]
0x1800df625  lea     rcx, [rbp+40h+var_40]
0x1800df629  call    ??$DuplicateString@U_UNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Windows@@@Rtl@StringUtil@Windows@@YAJAEBU_UNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::DuplicateString<_UNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(_UNICODE_STRING const &,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>)
0x1800df62e  mov     ebx, eax
0x1800df630  test    eax, eax
0x1800df632  jns     short loc_1800DF669
0x1800df634  mov     rcx, qword ptr [rbp+40h+var_60+8]
0x1800df638  test    rcx, rcx
0x1800df63b  jz      short loc_1800DF642
0x1800df63d  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800df642  mov     eax, ebx
0x1800df644  mov     rcx, [rbp+40h+var_20]
0x1800df648  xor     rcx, rsp; StackCookie
0x1800df64b  call    __security_check_cookie
0x1800df650  lea     r11, [rsp+140h+var_10]
0x1800df658  mov     rbx, [r11+28h]
0x1800df65c  mov     rsi, [r11+30h]
0x1800df660  mov     rsp, r11
0x1800df663  pop     r14
0x1800df665  pop     rdi
0x1800df666  pop     rbp
0x1800df667  retn
0x1800df669  lea     rax, [rbp+40h+var_60]
0x1800df66d  mov     [rsp+140h+var_120], rax
0x1800df672  lea     rcx, [rsp+140h+var_120]
0x1800df677  call    ??$EnsureTrailingNtPathSlash@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Windows@@@Rtl@StringUtil@Windows@@YAJV?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::EnsureTrailingNtPathSlash<Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>)
0x1800df67c  mov     ebx, eax
0x1800df67e  test    eax, eax
0x1800df680  js      short loc_1800DF634
0x1800df682  mov     qword ptr [rsp+140h+KeyObjectAttributes.Length], 30h ; '0'
0x1800df68b  mov     [rbp+40h+KeyObjectAttributes.RootDirectory], r14
0x1800df68f  lea     rax, [rbp+40h+var_40]
0x1800df693  mov     [rbp+40h+KeyObjectAttributes.ObjectName], rax
0x1800df697  mov     qword ptr [rbp+40h+KeyObjectAttributes.Attributes], 40h ; '@'
0x1800df69f  xorps   xmm0, xmm0
0x1800df6a2  movdqu  xmmword ptr [rbp+40h+KeyObjectAttributes.SecurityDescriptor], xmm0
0x1800df6a7  mov     [rbp+40h+var_98], 30h ; '0'
0x1800df6af  mov     [rbp+40h+var_90], r14
0x1800df6b3  lea     rax, [rbp+40h+var_60]
0x1800df6b7  mov     [rbp+40h+var_88], rax
0x1800df6bb  mov     [rbp+40h+var_80], 40h ; '@'
0x1800df6c3  movdqu  [rbp+40h+var_78], xmm0
0x1800df6c8  mov     qword ptr [rsp+140h+FileObjectAttributes.Length], 30h ; '0'
0x1800df6d1  mov     [rsp+140h+FileObjectAttributes.RootDirectory], r14
0x1800df6d6  lea     rax, [rbp+40h+var_30]
0x1800df6da  mov     [rsp+140h+FileObjectAttributes.ObjectName], rax
0x1800df6df  mov     qword ptr [rsp+140h+FileObjectAttributes.Attributes], 40h ; '@'
0x1800df6e8  movdqu  xmmword ptr [rsp+140h+FileObjectAttributes.SecurityDescriptor], xmm0
0x1800df6ee  mov     [rbp+40h+var_50], r14
0x1800df6f2  mov     [rbp+40h+var_48], r14b
0x1800df6f6  cmp     [rdi], r14
0x1800df6f9  jnz     loc_1800DF922
0x1800df6ff  lea     rax, ?Privs@BackupRestorePrivilegeAcquisition@RtlSystemUtil@@0QBJB; long const near * const RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs
0x1800df706  mov     [rsp+140h+var_120], rax
0x1800df70b  mov     [rsp+140h+var_118], 3
0x1800df714  lea     rdx, [rsp+140h+var_120]
0x1800df719  lea     rcx, [rbp+40h+var_50]
0x1800df71d  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x1800df722  mov     ebx, eax
0x1800df724  test    eax, eax
0x1800df726  jns     short loc_1800DF736
0x1800df728  lea     rcx, [rbp+40h+var_50]; this
0x1800df72c  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x1800df731  jmp     loc_1800DF634
0x1800df736  mov     ebx, r14d
0x1800df739  mov     esi, r14d
0x1800df73c  mov     r9d, 4
0x1800df742  lea     r8, [rbp+40h+var_98]
0x1800df746  mov     edx, 20019h
0x1800df74b  mov     rcx, rdi
0x1800df74e  call    cs:__imp_NtOpenKeyEx
0x1800df755  nop     dword ptr [rax+rax+00h]
0x1800df75a  test    eax, eax
0x1800df75c  jns     loc_1800DF8ED
0x1800df762  mov     r8d, 2000h; Flags
0x1800df768  lea     rdx, [rsp+140h+FileObjectAttributes]; FileObjectAttributes
0x1800df76d  lea     rcx, [rsp+140h+KeyObjectAttributes]; KeyObjectAttributes
0x1800df772  call    cs:__imp_NtLoadKey2
0x1800df779  nop     dword ptr [rax+rax+00h]
0x1800df77e  mov     ebx, eax
0x1800df780  cmp     eax, 0C00000F1h
0x1800df785  jnz     short loc_1800DF7A2
0x1800df787  xor     r8d, r8d; Flags
0x1800df78a  lea     rdx, [rsp+140h+FileObjectAttributes]; FileObjectAttributes
0x1800df78f  lea     rcx, [rsp+140h+KeyObjectAttributes]; KeyObjectAttributes
0x1800df794  call    cs:__imp_NtLoadKey2
0x1800df79b  nop     dword ptr [rax+rax+00h]
0x1800df7a0  mov     ebx, eax
0x1800df7a2  test    ebx, ebx
0x1800df7a4  jns     short loc_1800DF7F0
0x1800df7a6  cmp     ebx, 0C0000043h
0x1800df7ac  jnz     short loc_1800DF7C8
0x1800df7ae  mov     ecx, 0C8h
0x1800df7b3  call    DelayExecution
0x1800df7b8  inc     esi
0x1800df7ba  cmp     esi, 14h
0x1800df7bd  jle     loc_1800DF73C
0x1800df7c3  jmp     loc_1800DF8F5
0x1800df7c8  lea     rax, aOnecoreInterna_12; "OneCore\\internal\\Base\\inc\\auto_hive"...
0x1800df7cf  mov     [rsp+140h+var_120], rax
0x1800df7d4  lea     rax, aWindowsRtlAuto_0; "Windows::Rtl::AutoHive::Load"
0x1800df7db  mov     [rsp+140h+var_118], rax
0x1800df7e0  mov     [rsp+140h+var_110], 0E4h
0x1800df7e9  mov     [rsp+140h+var_108], r14
0x1800df7ee  jmp     short loc_1800DF841
0x1800df7f0  mov     r9d, 4
0x1800df7f6  lea     r8, [rbp+40h+var_98]
0x1800df7fa  mov     edx, 20019h
0x1800df7ff  mov     rcx, rdi
0x1800df802  call    cs:__imp_NtOpenKeyEx
0x1800df809  nop     dword ptr [rax+rax+00h]
0x1800df80e  mov     ebx, eax
0x1800df810  test    eax, eax
0x1800df812  jns     short loc_1800DF85A
0x1800df814  lea     rax, aOnecoreInterna_12; "OneCore\\internal\\Base\\inc\\auto_hive"...
0x1800df81b  mov     [rsp+140h+var_120], rax
0x1800df820  lea     rax, aWindowsRtlAuto_0; "Windows::Rtl::AutoHive::Load"
0x1800df827  mov     [rsp+140h+var_118], rax
0x1800df82c  mov     [rsp+140h+var_110], 0AEh
0x1800df835  lea     rax, aNtopenkeyexMRo; "NtOpenKeyEx(&m_RootKey, ((((0x00020000L"...
0x1800df83c  mov     [rsp+140h+var_108], rax
0x1800df841  mov     r8d, ebx
0x1800df844  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1800df84b  lea     rcx, [rsp+140h+var_120]
0x1800df850  call    RtlReportErrorOrigination
0x1800df855  jmp     loc_1800DF728
0x1800df85a  mov     byte ptr [rdi+28h], 1
0x1800df85e  movzx   ecx, word ptr [rbp+40h+var_60]
0x1800df862  mov     r8d, 2
0x1800df868  cmp     cx, r8w
0x1800df86c  jb      short loc_1800DF897
0x1800df86e  mov     rdx, qword ptr [rbp+40h+var_60+8]
0x1800df872  movzx   eax, cx
0x1800df875  shr     rax, 1
0x1800df878  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x1800df87e  jnz     short loc_1800DF897
0x1800df880  test    cx, cx
0x1800df883  jz      loc_1800DF922
0x1800df889  sub     cx, r8w
0x1800df88d  mov     word ptr [rbp+40h+var_60], cx
0x1800df891  cmp     cx, r8w
0x1800df895  jnb     short loc_1800DF872
0x1800df897  movups  xmm1, xmmword ptr [rdi+8]
0x1800df89b  movaps  xmm0, [rbp+40h+var_60]
0x1800df89f  movdqu  xmmword ptr [rdi+8], xmm0
0x1800df8a4  movdqa  [rbp+40h+var_60], xmm1
0x1800df8a9  mov     [rdi+2Ch], r8d
0x1800df8ad  lea     rax, [rdi+18h]
0x1800df8b1  mov     [rsp+140h+var_120], rax
0x1800df8b6  lea     rdx, [rsp+140h+var_120]
0x1800df8bb  lea     rcx, [rbp+40h+var_30]
0x1800df8bf  call    ??$DuplicateString@U_UNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Windows@@@Rtl@StringUtil@Windows@@YAJAEBU_UNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::DuplicateString<_UNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(_UNICODE_STRING const &,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>)
0x1800df8c4  mov     ebx, eax
0x1800df8c6  lea     rcx, [rbp+40h+var_50]; this
0x1800df8ca  test    eax, eax
0x1800df8cc  js      loc_1800DF72C
0x1800df8d2  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x1800df8d7  nop
0x1800df8d8  mov     rcx, qword ptr [rbp+40h+var_60+8]
0x1800df8dc  test    rcx, rcx
0x1800df8df  jz      short loc_1800DF8E6
0x1800df8e1  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800df8e6  xor     eax, eax
0x1800df8e8  jmp     loc_1800DF644
0x1800df8ed  test    ebx, ebx
0x1800df8ef  jns     loc_1800DF85E
0x1800df8f5  lea     rax, aOnecoreInterna_12; "OneCore\\internal\\Base\\inc\\auto_hive"...
0x1800df8fc  mov     [rsp+140h+var_120], rax
0x1800df901  lea     rax, aWindowsRtlAuto_0; "Windows::Rtl::AutoHive::Load"
0x1800df908  mov     [rsp+140h+var_118], rax
0x1800df90d  mov     [rsp+140h+var_110], 0F2h
0x1800df916  lea     rax, aStatus; "Status"
0x1800df91d  jmp     loc_1800DF83C
0x1800df922  mov     ecx, 0C00000E5h; int
0x1800df927  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
