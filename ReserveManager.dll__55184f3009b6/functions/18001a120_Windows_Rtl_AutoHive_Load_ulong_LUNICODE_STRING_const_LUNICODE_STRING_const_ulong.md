# Windows::Rtl::AutoHive::Load(ulong,_LUNICODE_STRING const &,_LUNICODE_STRING const &,ulong *)

- ea: `0x18001a120`
- end: `0x18001a5ac`
- name: `?Load@AutoHive@Rtl@Windows@@QEAAJKAEBU_LUNICODE_STRING@@0PEAK@Z`
- size: `1164`
- prototype: `__int64 __fastcall(Windows::Rtl::AutoHive *this, __int64, const struct _LUNICODE_STRING *, const struct _LUNICODE_STRING *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a5b4`

## callees

- `0x180003870`
- `0x180008140`
- `0x18000f904`
- `0x18000fafc`
- `0x180010794`
- `0x180010bdc`
- `0x180010d84`
- `0x180010ea4`
- `0x180010fe0`
- `0x180011958`
- `0x18001a120`

## import_xrefs

- `ntdll!NtLoadKey2` at `0x18001a380`
- `ntdll!NtLoadKey2` at `0x18001a380`
- `ntdll!NtOpenKeyEx` at `0x18001a367`
- `ntdll!NtOpenKeyEx` at `0x18001a3c6`
- `ntdll!NtOpenKeyEx` at `0x18001a367`
- `ntdll!NtOpenKeyEx` at `0x18001a3c6`

## string_xrefs

- `0x18001a3f3`: `NtOpenKeyEx(&m_RootKey, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))), &RootKeyAttributes, (0x00000004L))`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::AutoHive::Load(
        Windows::Rtl::AutoHive *this,
        __int64 a2,
        const struct _LUNICODE_STRING *a3,
        const struct _LUNICODE_STRING *a4)
{
  __int64 result; // rax
  struct _UNICODE_STRING *v7; // r8
  int v8; // ebx
  unsigned __int16 v9; // r8
  __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  int v12; // esi
  NTSTATUS v13; // eax
  unsigned __int16 i; // cx
  __int128 v15; // xmm1
  const char *v16; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h]
  __int64 v18; // [rsp+30h] [rbp-D0h]
  const char *v19; // [rsp+38h] [rbp-C8h]
  char v20; // [rsp+44h] [rbp-BCh]
  __int16 v21; // [rsp+45h] [rbp-BBh]
  char v22; // [rsp+47h] [rbp-B9h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  _QWORD v24[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+70h] [rbp-90h]
  struct _OBJECT_ATTRIBUTES FileObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES KeyObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v28; // [rsp+E0h] [rbp-20h] BYREF
  HANDLE v29; // [rsp+F0h] [rbp-10h] BYREF
  char v30; // [rsp+F8h] [rbp-8h]
  __int128 v31; // [rsp+100h] [rbp+0h] BYREF
  __int128 v32; // [rsp+110h] [rbp+10h] BYREF

  v23 = -2;
  v31 = 0;
  result = Windows::StringUtil::Rtl::CoerceStringShallow(
             a3,
             (const struct _LUNICODE_STRING *)&v31,
             (struct _UNICODE_STRING *)a3);
  if ( (int)result < 0 )
    return result;
  v32 = 0;
  result = Windows::StringUtil::Rtl::CoerceStringShallow(a4, (const struct _LUNICODE_STRING *)&v32, v7);
  if ( (int)result < 0 )
    return result;
  v28 = 0;
  v16 = (const char *)&v28;
  v8 = Windows::StringUtil::Rtl::DuplicateString<_UNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(
         &v31,
         &v16);
  if ( v8 < 0 )
  {
    if ( *((_QWORD *)&v28 + 1) )
      anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)&v28 + 1));
    return (unsigned int)v8;
  }
  v9 = v28;
  v10 = *((_QWORD *)&v28 + 1);
  if ( !(_WORD)v28 || *(_WORD *)(*((_QWORD *)&v28 + 1) + 2 * ((unsigned __int64)(unsigned __int16)v28 >> 1) - 2) != 92 )
  {
    v11 = WORD1(v28) - (unsigned __int64)(unsigned __int16)v28;
    if ( v11 < 2 )
    {
      HIDWORD(v16) = 0;
      v20 = 0;
      v21 = 0;
      v22 = 0;
      if ( (unsigned __int16)(v28 + 2) < (unsigned __int16)v28 )
      {
        v8 = -1073741675;
        goto LABEL_17;
      }
      v8 = RtlReallocateUnicodeString(v11, (unsigned __int16)(v28 + 2), &v28);
      v10 = *((_QWORD *)&v28 + 1);
      if ( v8 < 0 )
        goto LABEL_16;
      v9 = v28;
    }
    *(_WORD *)(v10 + 2 * ((unsigned __int64)v9 >> 1)) = 92;
    LOWORD(v28) = v28 + 2;
    v8 = 0;
    v10 = *((_QWORD *)&v28 + 1);
LABEL_16:
    if ( v8 < 0 )
    {
LABEL_17:
      if ( v10 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v10);
      return (unsigned int)v8;
    }
  }
  *(_QWORD *)&KeyObjectAttributes.Length = 48;
  KeyObjectAttributes.RootDirectory = 0;
  KeyObjectAttributes.ObjectName = (PUNICODE_STRING)&v31;
  *(_QWORD *)&KeyObjectAttributes.Attributes = 64;
  *(_OWORD *)&KeyObjectAttributes.SecurityDescriptor = 0;
  v24[0] = 48;
  v24[1] = 0;
  v24[2] = &v28;
  v24[3] = 64;
  v25 = 0;
  *(_QWORD *)&FileObjectAttributes.Length = 48;
  FileObjectAttributes.RootDirectory = 0;
  FileObjectAttributes.ObjectName = (PUNICODE_STRING)&v32;
  *(_QWORD *)&FileObjectAttributes.Attributes = 64;
  *(_OWORD *)&FileObjectAttributes.SecurityDescriptor = 0;
  v29 = 0;
  v30 = 0;
  if ( *(_QWORD *)this )
LABEL_55:
    INTERNAL_ERROR_ACTION(-1073741595);
  v16 = (const char *)&RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs;
  v17 = 3;
  v8 = RtlSystemUtil::PrivilegeAcquisition::Acquire((__int64)&v29, (__int64)&v16);
  if ( v8 < 0 )
  {
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v29);
    if ( *((_QWORD *)&v28 + 1) )
      anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)&v28 + 1));
    return (unsigned int)v8;
  }
  v8 = 0;
  v12 = 0;
  while ( 1 )
  {
    if ( (int)NtOpenKeyEx(this, 131097, v24, 4, v16, v17) >= 0 )
    {
      if ( v8 < 0 )
      {
LABEL_49:
        v16 = "OneCore\\Internal\\Base\\inc\\auto_hive.h";
        v17 = (__int64)"Windows::Rtl::AutoHive::Load";
        v18 = 242;
        v19 = "Status";
        RtlReportErrorOrigination(&v16, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v8);
        RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v29);
        if ( *((_QWORD *)&v28 + 1) )
          anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)&v28 + 1));
        return (unsigned int)v8;
      }
      goto LABEL_37;
    }
    v13 = NtLoadKey2(&KeyObjectAttributes, &FileObjectAttributes, 0);
    v8 = v13;
    if ( v13 == -1073741583 )
      goto LABEL_45;
    if ( v13 >= 0 )
      break;
    if ( v13 != -1073741757 )
    {
LABEL_45:
      v16 = "OneCore\\Internal\\Base\\inc\\auto_hive.h";
      v17 = (__int64)"Windows::Rtl::AutoHive::Load";
      v18 = 228;
      v19 = 0;
      RtlReportErrorOrigination(&v16, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v13);
      RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v29);
      if ( *((_QWORD *)&v28 + 1) )
        anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)&v28 + 1));
      return (unsigned int)v8;
    }
    DelayExecution();
    if ( ++v12 > 20 )
      goto LABEL_49;
  }
  v8 = NtOpenKeyEx(this, 131097, v24, 4, v16, v17);
  if ( v8 < 0 )
  {
    v16 = "OneCore\\Internal\\Base\\inc\\auto_hive.h";
    v17 = (__int64)"Windows::Rtl::AutoHive::Load";
    v18 = 174;
    v19 = "NtOpenKeyEx(&m_RootKey, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))), &RootKeyAttri"
          "butes, (0x00000004L))";
    RtlReportErrorOrigination(&v16, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v8);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v29);
    if ( *((_QWORD *)&v28 + 1) )
      anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)&v28 + 1));
    return (unsigned int)v8;
  }
  *((_BYTE *)this + 40) = 1;
LABEL_37:
  for ( i = v28; i >= 2u; LOWORD(v28) = i )
  {
    if ( *(_WORD *)(*((_QWORD *)&v28 + 1) + 2 * ((unsigned __int64)i >> 1) - 2) != 92 )
      break;
    if ( !i )
      goto LABEL_55;
    i -= 2;
  }
  v15 = *(_OWORD *)((char *)this + 8);
  *(_OWORD *)((char *)this + 8) = v28;
  v28 = v15;
  *((_DWORD *)this + 11) = 0;
  v16 = (char *)this + 24;
  v8 = Windows::StringUtil::Rtl::DuplicateString<_UNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(
         &v32,
         &v16);
  if ( v8 < 0 )
  {
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v29);
    if ( *((_QWORD *)&v28 + 1) )
      anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)&v28 + 1));
    return (unsigned int)v8;
  }
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v29);
  if ( *((_QWORD *)&v28 + 1) )
    anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)&v28 + 1));
  return 0;
}

```

## disassembly

```asm
0x18001a120  push    rbp
0x18001a122  push    rbx
0x18001a123  push    rsi
0x18001a124  push    rdi
0x18001a125  push    r14
0x18001a127  push    r15
0x18001a129  lea     rbp, [rsp-38h]
0x18001a12e  sub     rsp, 138h
0x18001a135  mov     [rsp+160h+var_118], 0FFFFFFFFFFFFFFFEh
0x18001a13e  mov     rax, cs:__security_cookie
0x18001a145  xor     rax, rsp
0x18001a148  mov     [rbp+60h+var_40], rax
0x18001a14c  mov     rbx, r9
0x18001a14f  mov     rdi, rcx
0x18001a152  xorps   xmm0, xmm0
0x18001a155  movups  [rbp+60h+var_60], xmm0
0x18001a159  lea     rdx, [rbp+60h+var_60]; struct _LUNICODE_STRING *
0x18001a15d  mov     rcx, r8; this
0x18001a160  call    ?CoerceStringShallow@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAU_UNICODE_STRING@@@Z; Windows::StringUtil::Rtl::CoerceStringShallow(_LUNICODE_STRING const &,_UNICODE_STRING *)
0x18001a165  xor     r14d, r14d
0x18001a168  test    eax, eax
0x18001a16a  js      short loc_18001A1B8
0x18001a16c  xorps   xmm0, xmm0
0x18001a16f  movups  [rbp+60h+var_50], xmm0
0x18001a173  lea     rdx, [rbp+60h+var_50]; struct _LUNICODE_STRING *
0x18001a177  mov     rcx, rbx; this
0x18001a17a  call    ?CoerceStringShallow@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAU_UNICODE_STRING@@@Z; Windows::StringUtil::Rtl::CoerceStringShallow(_LUNICODE_STRING const &,_UNICODE_STRING *)
0x18001a17f  test    eax, eax
0x18001a181  js      short loc_18001A1B8
0x18001a183  xorps   xmm0, xmm0
0x18001a186  movups  [rbp+60h+var_80], xmm0
0x18001a18a  lea     rax, [rbp+60h+var_80]
0x18001a18e  mov     [rsp+160h+var_140], rax
0x18001a193  lea     rdx, [rsp+160h+var_140]
0x18001a198  lea     rcx, [rbp+60h+var_60]
0x18001a19c  call    ??$DuplicateString@U_UNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Windows@@@Rtl@StringUtil@Windows@@YAJAEBU_UNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::DuplicateString<_UNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(_UNICODE_STRING const &,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>)
0x18001a1a1  mov     ebx, eax
0x18001a1a3  test    eax, eax
0x18001a1a5  jns     short loc_18001A1D4
0x18001a1a7  mov     rcx, qword ptr [rbp+60h+var_80+8]
0x18001a1ab  test    rcx, rcx
0x18001a1ae  jz      short loc_18001A1B6
0x18001a1b0  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a1b5  nop
0x18001a1b6  mov     eax, ebx
0x18001a1b8  mov     rcx, [rbp+60h+var_40]
0x18001a1bc  xor     rcx, rsp; StackCookie
0x18001a1bf  call    __security_check_cookie
0x18001a1c4  add     rsp, 138h
0x18001a1cb  pop     r15
0x18001a1cd  pop     r14
0x18001a1cf  pop     rdi
0x18001a1d0  pop     rsi
0x18001a1d1  pop     rbx
0x18001a1d2  pop     rbp
0x18001a1d3  retn
0x18001a1d4  movzx   r8d, word ptr [rbp+60h+var_80]
0x18001a1d9  mov     esi, 5Ch ; '\'
0x18001a1de  lea     r15d, [rsi-5Ah]
0x18001a1e2  mov     rdx, qword ptr [rbp+60h+var_80+8]
0x18001a1e6  test    r8w, r8w
0x18001a1ea  jz      short loc_18001A1FD
0x18001a1ec  mov     eax, r8d
0x18001a1ef  shr     rax, 1
0x18001a1f2  cmp     [rdx+rax*2-2], si
0x18001a1f7  jz      loc_18001A28B
0x18001a1fd  movzx   ecx, word ptr [rbp+60h+var_80+2]
0x18001a201  sub     rcx, r8
0x18001a204  cmp     rcx, r15
0x18001a207  jnb     short loc_18001A25D
0x18001a209  mov     dword ptr [rsp+160h+var_140+4], r14d
0x18001a20e  mov     byte ptr [rsp+160h+var_11C], r14b
0x18001a213  movzx   eax, word ptr [rsp+160h+var_140+5]
0x18001a218  mov     word ptr [rsp+160h+var_11C+1], ax
0x18001a21d  mov     al, byte ptr [rsp+160h+var_140+7]
0x18001a221  mov     byte ptr [rsp+160h+var_11C+3], al
0x18001a225  mov     ebx, [rsp+160h+var_11C]
0x18001a229  test    ebx, ebx
0x18001a22b  js      short loc_18001A278
0x18001a22d  lea     eax, [r15+r8]
0x18001a231  cmp     ax, r8w
0x18001a235  jb      short loc_18001A254
0x18001a237  movzx   edx, ax
0x18001a23a  lea     r8, [rbp+60h+var_80]
0x18001a23e  call    RtlReallocateUnicodeString
0x18001a243  mov     ebx, eax
0x18001a245  mov     rdx, qword ptr [rbp+60h+var_80+8]
0x18001a249  test    eax, eax
0x18001a24b  js      short loc_18001A274
0x18001a24d  movzx   r8d, word ptr [rbp+60h+var_80]
0x18001a252  jmp     short loc_18001A25D
0x18001a254  mov     ebx, 0C0000095h
0x18001a259  test    ebx, ebx
0x18001a25b  js      short loc_18001A278
0x18001a25d  movzx   eax, r8w
0x18001a261  shr     rax, 1
0x18001a264  mov     [rdx+rax*2], si
0x18001a268  add     word ptr [rbp+60h+var_80], r15w
0x18001a26d  mov     ebx, r14d
0x18001a270  mov     rdx, qword ptr [rbp+60h+var_80+8]
0x18001a274  test    ebx, ebx
0x18001a276  jns     short loc_18001A28B
0x18001a278  test    rdx, rdx
0x18001a27b  jz      short loc_18001A286
0x18001a27d  mov     rcx, rdx
0x18001a280  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a285  nop
0x18001a286  jmp     loc_18001A1B6
0x18001a28b  mov     qword ptr [rbp+60h+KeyObjectAttributes.Length], 30h ; '0'
0x18001a293  mov     [rbp+60h+KeyObjectAttributes.RootDirectory], r14
0x18001a297  lea     rax, [rbp+60h+var_60]
0x18001a29b  mov     [rbp+60h+KeyObjectAttributes.ObjectName], rax
0x18001a29f  mov     qword ptr [rbp+60h+KeyObjectAttributes.Attributes], 40h ; '@'
0x18001a2a7  xorps   xmm0, xmm0
0x18001a2aa  movdqu  xmmword ptr [rbp+60h+KeyObjectAttributes.SecurityDescriptor], xmm0
0x18001a2af  mov     [rsp+160h+var_110], 30h ; '0'
0x18001a2b8  mov     [rsp+160h+var_108], r14
0x18001a2bd  lea     rax, [rbp+60h+var_80]
0x18001a2c1  mov     [rsp+160h+var_100], rax
0x18001a2c6  mov     [rsp+160h+var_F8], 40h ; '@'
0x18001a2cf  movdqu  [rsp+160h+var_F0], xmm0
0x18001a2d5  mov     qword ptr [rbp+60h+FileObjectAttributes.Length], 30h ; '0'
0x18001a2dd  mov     [rbp+60h+FileObjectAttributes.RootDirectory], r14
0x18001a2e1  lea     rax, [rbp+60h+var_50]
0x18001a2e5  mov     [rbp+60h+FileObjectAttributes.ObjectName], rax
0x18001a2e9  mov     qword ptr [rbp+60h+FileObjectAttributes.Attributes], 40h ; '@'
0x18001a2f1  movdqu  xmmword ptr [rbp+60h+FileObjectAttributes.SecurityDescriptor], xmm0
0x18001a2f6  mov     [rbp+60h+var_70], r14
0x18001a2fa  mov     [rbp+60h+var_68], r14b
0x18001a2fe  cmp     [rdi], r14
0x18001a301  jnz     loc_18001A5A1
0x18001a307  lea     rax, ?Privs@BackupRestorePrivilegeAcquisition@RtlSystemUtil@@0QBJB; long const near * const RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs
0x18001a30e  mov     [rsp+160h+var_140], rax
0x18001a313  mov     [rsp+160h+var_138], 3
0x18001a31c  lea     rdx, [rsp+160h+var_140]
0x18001a321  lea     rcx, [rbp+60h+var_70]
0x18001a325  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x18001a32a  mov     ebx, eax
0x18001a32c  test    eax, eax
0x18001a32e  jns     short loc_18001A34E
0x18001a330  lea     rcx, [rbp+60h+var_70]; this
0x18001a334  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001a339  nop
0x18001a33a  mov     rcx, qword ptr [rbp+60h+var_80+8]
0x18001a33e  test    rcx, rcx
0x18001a341  jz      short loc_18001A349
0x18001a343  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a348  nop
0x18001a349  jmp     loc_18001A1B6
0x18001a34e  mov     ebx, r14d
0x18001a351  mov     esi, r14d
0x18001a354  mov     r9d, 4
0x18001a35a  lea     r8, [rsp+160h+var_110]
0x18001a35f  mov     edx, 20019h
0x18001a364  mov     rcx, rdi
0x18001a367  call    cs:__imp_NtOpenKeyEx
0x18001a36d  test    eax, eax
0x18001a36f  jns     loc_18001A51D
0x18001a375  xor     r8d, r8d; Flags
0x18001a378  lea     rdx, [rbp+60h+FileObjectAttributes]; FileObjectAttributes
0x18001a37c  lea     rcx, [rbp+60h+KeyObjectAttributes]; KeyObjectAttributes
0x18001a380  call    cs:__imp_NtLoadKey2
0x18001a386  mov     ebx, eax
0x18001a388  cmp     eax, 0C00000F1h
0x18001a38d  jz      loc_18001A4C4
0x18001a393  test    eax, eax
0x18001a395  jns     short loc_18001A3B3
0x18001a397  cmp     eax, 0C0000043h
0x18001a39c  jnz     loc_18001A4C4
0x18001a3a2  call    DelayExecution
0x18001a3a7  inc     esi
0x18001a3a9  cmp     esi, 14h
0x18001a3ac  jle     short loc_18001A354
0x18001a3ae  jmp     loc_18001A525
0x18001a3b3  mov     r9d, 4
0x18001a3b9  lea     r8, [rsp+160h+var_110]
0x18001a3be  mov     edx, 20019h
0x18001a3c3  mov     rcx, rdi
0x18001a3c6  call    cs:__imp_NtOpenKeyEx
0x18001a3cc  mov     ebx, eax
0x18001a3ce  test    eax, eax
0x18001a3d0  jns     short loc_18001A432
0x18001a3d2  lea     rcx, aOnecoreInterna_2; "OneCore\\Internal\\Base\\inc\\auto_hive"...
0x18001a3d9  mov     [rsp+160h+var_140], rcx
0x18001a3de  lea     rcx, aWindowsRtlAuto_0; "Windows::Rtl::AutoHive::Load"
0x18001a3e5  mov     [rsp+160h+var_138], rcx
0x18001a3ea  mov     [rsp+160h+var_130], 0AEh
0x18001a3f3  lea     rax, aNtopenkeyexMRo; "NtOpenKeyEx(&m_RootKey, ((((0x00020000L"...
0x18001a3fa  mov     [rsp+160h+var_128], rax
0x18001a3ff  mov     r8d, ebx
0x18001a402  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001a409  lea     rcx, [rsp+160h+var_140]
0x18001a40e  call    RtlReportErrorOrigination
0x18001a413  nop
0x18001a414  lea     rcx, [rbp+60h+var_70]; this
0x18001a418  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001a41d  nop
0x18001a41e  mov     rcx, qword ptr [rbp+60h+var_80+8]
0x18001a422  test    rcx, rcx
0x18001a425  jz      short loc_18001A42D
0x18001a427  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a42c  nop
0x18001a42d  jmp     loc_18001A1B6
0x18001a432  mov     byte ptr [rdi+28h], 1
0x18001a436  movzx   ecx, word ptr [rbp+60h+var_80]
0x18001a43a  cmp     cx, r15w
0x18001a43e  jb      short loc_18001A46F
0x18001a440  mov     rdx, qword ptr [rbp+60h+var_80+8]
0x18001a444  mov     r8d, 5Ch ; '\'
0x18001a44a  movzx   eax, cx
0x18001a44d  shr     rax, 1
0x18001a450  cmp     [rdx+rax*2-2], r8w
0x18001a456  jnz     short loc_18001A46F
0x18001a458  test    cx, cx
0x18001a45b  jz      loc_18001A5A1
0x18001a461  sub     cx, r15w
0x18001a465  mov     word ptr [rbp+60h+var_80], cx
0x18001a469  cmp     cx, r15w
0x18001a46d  jnb     short loc_18001A44A
0x18001a46f  movups  xmm1, xmmword ptr [rdi+8]
0x18001a473  movaps  xmm0, [rbp+60h+var_80]
0x18001a477  movdqu  xmmword ptr [rdi+8], xmm0
0x18001a47c  movdqa  [rbp+60h+var_80], xmm1
0x18001a481  mov     [rdi+2Ch], r14d
0x18001a485  lea     rax, [rdi+18h]
0x18001a489  mov     [rsp+160h+var_140], rax
0x18001a48e  lea     rdx, [rsp+160h+var_140]
0x18001a493  lea     rcx, [rbp+60h+var_50]
0x18001a497  call    ??$DuplicateString@U_UNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Windows@@@Rtl@StringUtil@Windows@@YAJAEBU_UNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::DuplicateString<_UNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(_UNICODE_STRING const &,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>)
0x18001a49c  mov     ebx, eax
0x18001a49e  lea     rcx, [rbp+60h+var_70]; this
0x18001a4a2  test    eax, eax
0x18001a4a4  jns     loc_18001A585
0x18001a4aa  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001a4af  nop
0x18001a4b0  mov     rcx, qword ptr [rbp+60h+var_80+8]
0x18001a4b4  test    rcx, rcx
0x18001a4b7  jz      short loc_18001A4BF
0x18001a4b9  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a4be  nop
0x18001a4bf  jmp     loc_18001A1B6
0x18001a4c4  lea     rcx, aOnecoreInterna_2; "OneCore\\Internal\\Base\\inc\\auto_hive"...
0x18001a4cb  mov     [rsp+160h+var_140], rcx
0x18001a4d0  lea     rcx, aWindowsRtlAuto_0; "Windows::Rtl::AutoHive::Load"
0x18001a4d7  mov     [rsp+160h+var_138], rcx
0x18001a4dc  mov     [rsp+160h+var_130], 0E4h
0x18001a4e5  mov     [rsp+160h+var_128], r14
0x18001a4ea  mov     r8d, ebx
0x18001a4ed  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001a4f4  lea     rcx, [rsp+160h+var_140]
0x18001a4f9  call    RtlReportErrorOrigination
0x18001a4fe  nop
0x18001a4ff  lea     rcx, [rbp+60h+var_70]; this
0x18001a503  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001a508  nop
0x18001a509  mov     rcx, qword ptr [rbp+60h+var_80+8]
0x18001a50d  test    rcx, rcx
0x18001a510  jz      short loc_18001A518
0x18001a512  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a517  nop
0x18001a518  jmp     loc_18001A1B6
0x18001a51d  test    ebx, ebx
0x18001a51f  jns     loc_18001A436
0x18001a525  lea     rcx, aOnecoreInterna_2; "OneCore\\Internal\\Base\\inc\\auto_hive"...
0x18001a52c  mov     [rsp+160h+var_140], rcx
0x18001a531  lea     rcx, aWindowsRtlAuto_0; "Windows::Rtl::AutoHive::Load"
0x18001a538  mov     [rsp+160h+var_138], rcx
0x18001a53d  mov     [rsp+160h+var_130], 0F2h
0x18001a546  lea     rax, aStatus; "Status"
0x18001a54d  mov     [rsp+160h+var_128], rax
0x18001a552  mov     r8d, ebx
0x18001a555  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001a55c  lea     rcx, [rsp+160h+var_140]
0x18001a561  call    RtlReportErrorOrigination
0x18001a566  nop
0x18001a567  lea     rcx, [rbp+60h+var_70]; this
0x18001a56b  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001a570  nop
0x18001a571  mov     rcx, qword ptr [rbp+60h+var_80+8]
0x18001a575  test    rcx, rcx
0x18001a578  jz      short loc_18001A580
0x18001a57a  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a57f  nop
0x18001a580  jmp     loc_18001A1B6
0x18001a585  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001a58a  nop
0x18001a58b  mov     rcx, qword ptr [rbp+60h+var_80+8]
0x18001a58f  test    rcx, rcx
0x18001a592  jz      short loc_18001A59A
0x18001a594  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a599  nop
0x18001a59a  xor     eax, eax
0x18001a59c  jmp     loc_18001A1B8
0x18001a5a1  mov     ecx, 0C00000E5h; int
0x18001a5a6  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
