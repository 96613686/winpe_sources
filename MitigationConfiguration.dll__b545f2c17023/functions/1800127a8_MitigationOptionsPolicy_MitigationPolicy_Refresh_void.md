# MitigationOptionsPolicy::MitigationPolicy::Refresh(void)

- ea: `0x1800127a8`
- end: `0x180012cc9`
- name: `?Refresh@MitigationPolicy@MitigationOptionsPolicy@@QEAA_NXZ`
- size: `1313`
- prototype: `char __fastcall(MitigationOptionsPolicy::ImagePolicy **this)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009f70`

## callees

- `0x180001c00`
- `0x1800074d8`
- `0x1800076b4`
- `0x180007768`
- `0x180011028`
- `0x180011304`
- `0x180011858`
- `0x180012530`
- `0x1800127a8`
- `0x180013a60`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18001287a`
- `ntdll!NtOpenKey` at `0x1800129c1`
- `ntdll!NtOpenKey` at `0x180012ad8`
- `ntdll!NtOpenKey` at `0x18001287a`
- `ntdll!NtOpenKey` at `0x1800129c1`
- `ntdll!NtOpenKey` at `0x180012ad8`
- `ntdll!RtlNtStatusToDosError` at `0x180012940`
- `ntdll!RtlNtStatusToDosError` at `0x180012bc7`
- `ntdll!RtlNtStatusToDosError` at `0x180012c71`
- `ntdll!RtlNtStatusToDosError` at `0x180012940`
- `ntdll!RtlNtStatusToDosError` at `0x180012bc7`
- `ntdll!RtlNtStatusToDosError` at `0x180012c71`
- `ntdll!NtClose` at `0x180012c2e`
- `ntdll!NtClose` at `0x180012c56`
- `ntdll!NtClose` at `0x180012c8a`
- `ntdll!NtClose` at `0x180012c9e`
- `ntdll!NtClose` at `0x180012c2e`
- `ntdll!NtClose` at `0x180012c56`
- `ntdll!NtClose` at `0x180012c8a`
- `ntdll!NtClose` at `0x180012c9e`
- `ntdll!NtQueryValueKey` at `0x1800129f4`
- `ntdll!NtQueryValueKey` at `0x180012b0b`
- `ntdll!NtQueryValueKey` at `0x1800129f4`
- `ntdll!NtQueryValueKey` at `0x180012b0b`
- `ntdll!NtEnumerateKey` at `0x1800128bc`
- `ntdll!NtEnumerateKey` at `0x180012a54`
- `ntdll!NtEnumerateKey` at `0x1800128bc`
- `ntdll!NtEnumerateKey` at `0x180012a54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012c79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012c79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bcf`

## pseudocode

```c
char __fastcall MitigationOptionsPolicy::MitigationPolicy::Refresh(MitigationOptionsPolicy::ImagePolicy **this)
{
  MitigationOptionsPolicy::ImagePolicy *v2; // rbx
  MitigationOptionsPolicy::ImagePolicy *v3; // rsi
  NTSTATUS v4; // eax
  NTSTATUS v5; // ecx
  ULONG v6; // r15d
  NTSTATUS v7; // ebx
  __int64 v8; // rax
  ULONG v9; // ebx
  ULONG v10; // r14d
  NTSTATUS v11; // esi
  int *v12; // rdx
  __int64 v13; // rax
  ULONG v14; // ebx
  DWORD v15; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v18; // [rsp+38h] [rbp-C8h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v23[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v24[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v25[3392]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v26[3392]; // [rsp+E10h] [rbp+D10h] BYREF
  _BYTE KeyInformation[4]; // [rsp+1B50h] [rbp+1A50h] BYREF
  int v28; // [rsp+1B54h] [rbp+1A54h]
  unsigned int v29; // [rsp+1B58h] [rbp+1A58h]
  int v30; // [rsp+1B5Ch] [rbp+1A5Ch] BYREF
  _WORD v31[4112]; // [rsp+1B60h] [rbp+1A60h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ResultLength = 0;
  v2 = *this;
  v3 = this[1];
  if ( *this != v3 )
  {
    do
    {
      MitigationOptionsPolicy::ImagePolicy::~ImagePolicy(v2);
      v2 = (MitigationOptionsPolicy::ImagePolicy *)((char *)v2 + 3392);
    }
    while ( v2 != v3 );
    this[1] = *this;
  }
  if ( !MitigationOptionsPolicy::ImagePolicy::Load((MitigationOptionsPolicy::ImagePolicy *)(this + 427)) )
    goto LABEL_46;
  MitigationOptionsPolicy::ImagePolicy::Load((MitigationOptionsPolicy::ImagePolicy *)(this + 3));
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_1800163A8;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenKey(&KeyHandle, 0x20119u, &ObjectAttributes);
  if ( v4 < 0 )
  {
    v5 = v4;
LABEL_45:
    v15 = RtlNtStatusToDosError(v5);
    SetLastError(v15);
LABEL_46:
    if ( KeyHandle )
      NtClose(KeyHandle);
    return 0;
  }
  v6 = 0;
  do
  {
    v22 = 0;
    v7 = NtEnumerateKey(KeyHandle, v6, KeyBasicInformation, KeyInformation, 0x2028u, &ResultLength);
    if ( v7 >= 0 && ResultLength != 8232 )
    {
      LOWORD(v22) = v30;
      WORD1(v22) = v30 + 2;
      *((_QWORD *)&v22 + 1) = v31;
      v31[(unsigned __int64)(unsigned __int16)v30 >> 1] = 0;
      v18 = 0;
      v8 = std::wstring::wstring(v23, *((_QWORD *)&v22 + 1));
      MitigationOptionsPolicy::ImagePolicy::ImagePolicy(v25, v8);
      std::wstring::~wstring(v23);
      if ( MitigationOptionsPolicy::ImagePolicy::Load((MitigationOptionsPolicy::ImagePolicy *)v25) )
      {
        v9 = RtlNtStatusToDosError(-1073741772);
        if ( GetLastError() != v9 )
        {
          if ( this[1] == this[2] )
          {
            std::vector<MitigationOptionsPolicy::ImagePolicy>::_Emplace_reallocate<MitigationOptionsPolicy::ImagePolicy const &>(
              this,
              this[1],
              v25);
          }
          else
          {
            MitigationOptionsPolicy::ImagePolicy::ImagePolicy(
              this[1],
              (const struct MitigationOptionsPolicy::ImagePolicy *)v25);
            this[1] = (MitigationOptionsPolicy::ImagePolicy *)((char *)this[1] + 3392);
          }
        }
      }
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v22;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtOpenKey(&v18, 0x20119u, &ObjectAttributes) >= 0
        && NtQueryValueKey(
             v18,
             (PUNICODE_STRING)&stru_180016398,
             KeyValuePartialInformation,
             KeyInformation,
             0x2028u,
             &ResultLength) >= 0
        && v28 == 4
        && v29 == 4
        && v30 )
      {
        v10 = 0;
        while ( 1 )
        {
          v23[0] = 0;
          v11 = NtEnumerateKey(v18, v10, KeyBasicInformation, KeyInformation, 0x2028u, &ResultLength);
          if ( v11 >= 0 && ResultLength != 8232 )
            break;
LABEL_39:
          ++v10;
          if ( v11 < 0 )
            goto LABEL_40;
        }
        LOWORD(v23[0]) = v30;
        WORD1(v23[0]) = v30 + 2;
        *((_QWORD *)&v23[0] + 1) = v31;
        v31[(unsigned __int64)(unsigned __int16)v30 >> 1] = 0;
        Handle = 0;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = v18;
        ObjectAttributes.Attributes = 576;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)v23;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( NtOpenKey(&Handle, 0x20119u, &ObjectAttributes) >= 0
          && (v11 = NtQueryValueKey(
                      Handle,
                      (PUNICODE_STRING)&stru_1800163B8,
                      KeyValuePartialInformation,
                      KeyInformation,
                      0x2028u,
                      &ResultLength),
              v11 >= 0)
          && v28 == 1
          && v29 <= 0xFFFE )
        {
          LOWORD(v23[0]) = v29 - 2;
          WORD1(v23[0]) = v29;
          v12 = &v30;
          *((_QWORD *)&v23[0] + 1) = &v30;
          if ( v31[((unsigned __int64)(unsigned __int16)(v29 - 2) >> 1) - 2] )
          {
            if ( ResultLength != 8232 )
            {
              LOWORD(v23[0]) = v29;
              v31[((unsigned __int64)(unsigned __int16)v29 >> 1) - 2] = 0;
              WORD1(v23[0]) += 2;
              v12 = (int *)*((_QWORD *)&v23[0] + 1);
              goto LABEL_30;
            }
          }
          else
          {
LABEL_30:
            v13 = std::wstring::wstring(v24, v12);
            MitigationOptionsPolicy::ImagePolicy::ImagePolicy(v26, v13);
            std::wstring::~wstring(v24);
            if ( MitigationOptionsPolicy::ImagePolicy::Load((MitigationOptionsPolicy::ImagePolicy *)v26) )
            {
              v14 = RtlNtStatusToDosError(-1073741772);
              if ( GetLastError() != v14 )
              {
                if ( this[1] == this[2] )
                {
                  std::vector<MitigationOptionsPolicy::ImagePolicy>::_Emplace_reallocate<MitigationOptionsPolicy::ImagePolicy const &>(
                    this,
                    this[1],
                    v26);
                }
                else
                {
                  MitigationOptionsPolicy::ImagePolicy::ImagePolicy(
                    this[1],
                    (const struct MitigationOptionsPolicy::ImagePolicy *)v26);
                  this[1] = (MitigationOptionsPolicy::ImagePolicy *)((char *)this[1] + 3392);
                }
              }
            }
            MitigationOptionsPolicy::ImagePolicy::~ImagePolicy((MitigationOptionsPolicy::ImagePolicy *)v26);
          }
        }
        else
        {
          v11 = 0;
        }
        if ( Handle )
          NtClose(Handle);
        goto LABEL_39;
      }
LABEL_40:
      v7 = 0;
      MitigationOptionsPolicy::ImagePolicy::~ImagePolicy((MitigationOptionsPolicy::ImagePolicy *)v25);
      if ( v18 )
        NtClose(v18);
    }
    ++v6;
  }
  while ( v7 >= 0 );
  if ( v7 != -2147483622 )
  {
    v5 = v7;
    goto LABEL_45;
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return 1;
}

```

## disassembly

```asm
0x1800127a8  push    rbp
0x1800127aa  push    rbx
0x1800127ab  push    rsi
0x1800127ac  push    rdi
0x1800127ad  push    r12
0x1800127af  push    r13
0x1800127b1  push    r14
0x1800127b3  push    r15
0x1800127b5  lea     rbp, [rsp-3A98h]
0x1800127bd  mov     eax, 3B98h
0x1800127c2  call    _alloca_probe
0x1800127c7  sub     rsp, rax
0x1800127ca  mov     rax, cs:__security_cookie
0x1800127d1  xor     rax, rsp
0x1800127d4  mov     [rbp+3AD0h+var_50], rax
0x1800127db  mov     rdi, rcx
0x1800127de  xor     r12d, r12d
0x1800127e1  mov     [rsp+3BD0h+KeyHandle], r12
0x1800127e6  xorps   xmm0, xmm0
0x1800127e9  movups  xmmword ptr [rsp+3BD0h+ObjectAttributes.Length], xmm0
0x1800127ee  movups  xmmword ptr [rsp+3BD0h+ObjectAttributes.ObjectName], xmm0
0x1800127f3  movups  xmmword ptr [rsp+3BD0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800127f8  mov     [rsp+3BD0h+var_3BA0], r12d
0x1800127fd  mov     rbx, [rcx]
0x180012800  mov     rsi, [rcx+8]
0x180012804  cmp     rbx, rsi
0x180012807  jz      short loc_180012824
0x180012809  mov     rcx, rbx; this
0x18001280c  call    ??1ImagePolicy@MitigationOptionsPolicy@@QEAA@XZ; MitigationOptionsPolicy::ImagePolicy::~ImagePolicy(void)
0x180012811  add     rbx, 0D40h
0x180012818  cmp     rbx, rsi
0x18001281b  jnz     short loc_180012809
0x18001281d  mov     rax, [rdi]
0x180012820  mov     [rdi+8], rax
0x180012824  lea     rcx, [rdi+0D58h]; this
0x18001282b  call    ?Load@ImagePolicy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::ImagePolicy::Load(void)
0x180012830  test    al, al
0x180012832  jz      loc_180012C80
0x180012838  lea     rcx, [rdi+18h]; this
0x18001283c  call    ?Load@ImagePolicy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::ImagePolicy::Load(void)
0x180012841  mov     [rsp+3BD0h+ObjectAttributes.Length], 30h ; '0'
0x180012849  mov     [rsp+3BD0h+ObjectAttributes.RootDirectory], r12
0x18001284e  mov     [rsp+3BD0h+ObjectAttributes.Attributes], 240h
0x180012856  lea     rax, qword_1800163A8
0x18001285d  mov     [rsp+3BD0h+ObjectAttributes.ObjectName], rax
0x180012862  xorps   xmm0, xmm0
0x180012865  movdqu  xmmword ptr [rsp+3BD0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001286b  lea     r8, [rsp+3BD0h+ObjectAttributes]; ObjectAttributes
0x180012870  mov     edx, 20119h; DesiredAccess
0x180012875  lea     rcx, [rsp+3BD0h+KeyHandle]; KeyHandle
0x18001287a  call    cs:__imp_NtOpenKey
0x180012880  test    eax, eax
0x180012882  jns     short loc_18001288B
0x180012884  mov     ecx, eax
0x180012886  jmp     loc_180012C71
0x18001288b  mov     r15d, r12d
0x18001288e  mov     r13d, 2028h
0x180012894  xorps   xmm0, xmm0
0x180012897  movups  [rbp+3AD0h+var_3B50], xmm0
0x18001289b  lea     rax, [rsp+3BD0h+var_3BA0]
0x1800128a0  mov     [rsp+3BD0h+ResultLength], rax; ResultLength
0x1800128a5  mov     [rsp+3BD0h+Length], r13d; Length
0x1800128aa  lea     r9, [rbp+3AD0h+KeyInformation]; KeyInformation
0x1800128b1  xor     r8d, r8d; KeyInformationClass
0x1800128b4  mov     edx, r15d; Index
0x1800128b7  mov     rcx, [rsp+3BD0h+KeyHandle]; KeyHandle
0x1800128bc  call    cs:__imp_NtEnumerateKey
0x1800128c2  mov     ebx, eax
0x1800128c4  test    eax, eax
0x1800128c6  js      loc_180012C5C
0x1800128cc  cmp     [rsp+3BD0h+var_3BA0], r13d
0x1800128d1  jz      loc_180012C5C
0x1800128d7  movzx   ecx, word ptr [rbp+3AD0h+var_2074]
0x1800128de  mov     word ptr [rbp+3AD0h+var_3B50], cx
0x1800128e2  mov     ebx, 2
0x1800128e7  lea     eax, [rbx+rcx]
0x1800128ea  mov     word ptr [rbp+3AD0h+var_3B50+2], ax
0x1800128ee  lea     rax, [rbp+3AD0h+var_2070]
0x1800128f5  mov     qword ptr [rbp+3AD0h+var_3B50+8], rax
0x1800128f9  shr     rcx, 1
0x1800128fc  mov     [rbp+rcx*2+3AD0h+var_2070], r12w
0x180012905  mov     [rsp+3BD0h+var_3B98], r12
0x18001290a  mov     rdx, qword ptr [rbp+3AD0h+var_3B50+8]
0x18001290e  lea     rcx, [rbp+3AD0h+var_3B40]
0x180012912  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180012917  nop
0x180012918  mov     rdx, rax
0x18001291b  lea     rcx, [rbp+3AD0h+var_3B00]
0x18001291f  call    ??0ImagePolicy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MitigationOptionsPolicy::ImagePolicy::ImagePolicy(std::wstring const &)
0x180012924  nop
0x180012925  lea     rcx, [rbp+3AD0h+var_3B40]
0x180012929  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001292e  lea     rcx, [rbp+3AD0h+var_3B00]; this
0x180012932  call    ?Load@ImagePolicy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::ImagePolicy::Load(void)
0x180012937  test    al, al
0x180012939  jz      short loc_180012986
0x18001293b  mov     ecx, 0C0000034h; Status
0x180012940  call    cs:__imp_RtlNtStatusToDosError
0x180012946  mov     ebx, eax
0x180012948  call    cs:__imp_GetLastError
0x18001294e  cmp     eax, ebx
0x180012950  jz      short loc_180012981
0x180012952  mov     rax, [rdi+8]
0x180012956  cmp     rax, [rdi+10h]
0x18001295a  jz      short loc_180012972
0x18001295c  lea     rdx, [rbp+3AD0h+var_3B00]; struct MitigationOptionsPolicy::ImagePolicy *
0x180012960  mov     rcx, rax; this
0x180012963  call    ??0ImagePolicy@MitigationOptionsPolicy@@QEAA@AEBV01@@Z; MitigationOptionsPolicy::ImagePolicy::ImagePolicy(MitigationOptionsPolicy::ImagePolicy const &)
0x180012968  add     qword ptr [rdi+8], 0D40h
0x180012970  jmp     short loc_180012981
0x180012972  lea     r8, [rbp+3AD0h+var_3B00]
0x180012976  mov     rdx, rax
0x180012979  mov     rcx, rdi
0x18001297c  call    ??$_Emplace_reallocate@AEBVImagePolicy@MitigationOptionsPolicy@@@?$vector@VImagePolicy@MitigationOptionsPolicy@@V?$allocator@VImagePolicy@MitigationOptionsPolicy@@@std@@@std@@AEAAPEAVImagePolicy@MitigationOptionsPolicy@@QEAV23@AEBV23@@Z; std::vector<MitigationOptionsPolicy::ImagePolicy>::_Emplace_reallocate<MitigationOptionsPolicy::ImagePolicy const &>(MitigationOptionsPolicy::ImagePolicy * const,MitigationOptionsPolicy::ImagePolicy const &)
0x180012981  mov     ebx, 2
0x180012986  mov     [rsp+3BD0h+ObjectAttributes.Length], 30h ; '0'
0x18001298e  mov     rax, [rsp+3BD0h+KeyHandle]
0x180012993  mov     [rsp+3BD0h+ObjectAttributes.RootDirectory], rax
0x180012998  mov     [rsp+3BD0h+ObjectAttributes.Attributes], 240h
0x1800129a0  lea     rax, [rbp+3AD0h+var_3B50]
0x1800129a4  mov     [rsp+3BD0h+ObjectAttributes.ObjectName], rax
0x1800129a9  xorps   xmm0, xmm0
0x1800129ac  movdqu  xmmword ptr [rsp+3BD0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800129b2  lea     r8, [rsp+3BD0h+ObjectAttributes]; ObjectAttributes
0x1800129b7  mov     edx, 20119h; DesiredAccess
0x1800129bc  lea     rcx, [rsp+3BD0h+var_3B98]; KeyHandle
0x1800129c1  call    cs:__imp_NtOpenKey
0x1800129c7  test    eax, eax
0x1800129c9  js      loc_180012C3F
0x1800129cf  lea     rax, [rsp+3BD0h+var_3BA0]
0x1800129d4  mov     [rsp+3BD0h+ResultLength], rax; ResultLength
0x1800129d9  mov     [rsp+3BD0h+Length], r13d; Length
0x1800129de  lea     r9, [rbp+3AD0h+KeyInformation]; KeyValueInformation
0x1800129e5  mov     r8d, ebx; KeyValueInformationClass
0x1800129e8  lea     rdx, stru_180016398; ValueName
0x1800129ef  mov     rcx, [rsp+3BD0h+var_3B98]; KeyHandle
0x1800129f4  call    cs:__imp_NtQueryValueKey
0x1800129fa  test    eax, eax
0x1800129fc  js      loc_180012C3F
0x180012a02  cmp     [rbp+3AD0h+var_207C], 4
0x180012a09  jnz     loc_180012C3F
0x180012a0f  cmp     [rbp+3AD0h+var_2078], 4
0x180012a16  jnz     loc_180012C3F
0x180012a1c  cmp     [rbp+3AD0h+var_2074], r12d
0x180012a23  jz      loc_180012C3F
0x180012a29  mov     r14d, r12d
0x180012a2c  xorps   xmm0, xmm0
0x180012a2f  movups  [rbp+3AD0h+var_3B40], xmm0
0x180012a33  lea     rax, [rsp+3BD0h+var_3BA0]
0x180012a38  mov     [rsp+3BD0h+ResultLength], rax; ResultLength
0x180012a3d  mov     [rsp+3BD0h+Length], r13d; Length
0x180012a42  lea     r9, [rbp+3AD0h+KeyInformation]; KeyInformation
0x180012a49  xor     r8d, r8d; KeyInformationClass
0x180012a4c  mov     edx, r14d; Index
0x180012a4f  mov     rcx, [rsp+3BD0h+var_3B98]; KeyHandle
0x180012a54  call    cs:__imp_NtEnumerateKey
0x180012a5a  mov     esi, eax
0x180012a5c  test    eax, eax
0x180012a5e  js      loc_180012C34
0x180012a64  cmp     [rsp+3BD0h+var_3BA0], r13d
0x180012a69  jz      loc_180012C34
0x180012a6f  movzx   ecx, word ptr [rbp+3AD0h+var_2074]
0x180012a76  mov     word ptr [rbp+3AD0h+var_3B40], cx
0x180012a7a  lea     eax, [rbx+rcx]
0x180012a7d  mov     word ptr [rbp+3AD0h+var_3B40+2], ax
0x180012a81  lea     rax, [rbp+3AD0h+var_2070]
0x180012a88  mov     qword ptr [rbp+3AD0h+var_3B40+8], rax
0x180012a8c  shr     rcx, 1
0x180012a8f  mov     [rbp+rcx*2+3AD0h+var_2070], r12w
0x180012a98  mov     [rsp+3BD0h+Handle], r12
0x180012a9d  mov     [rsp+3BD0h+ObjectAttributes.Length], 30h ; '0'
0x180012aa5  mov     rax, [rsp+3BD0h+var_3B98]
0x180012aaa  mov     [rsp+3BD0h+ObjectAttributes.RootDirectory], rax
0x180012aaf  mov     [rsp+3BD0h+ObjectAttributes.Attributes], 240h
0x180012ab7  lea     rax, [rbp+3AD0h+var_3B40]
0x180012abb  mov     [rsp+3BD0h+ObjectAttributes.ObjectName], rax
0x180012ac0  xorps   xmm0, xmm0
0x180012ac3  movdqu  xmmword ptr [rsp+3BD0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180012ac9  lea     r8, [rsp+3BD0h+ObjectAttributes]; ObjectAttributes
0x180012ace  mov     edx, 20119h; DesiredAccess
0x180012ad3  lea     rcx, [rsp+3BD0h+Handle]; KeyHandle
0x180012ad8  call    cs:__imp_NtOpenKey
0x180012ade  test    eax, eax
0x180012ae0  js      loc_180012C21
0x180012ae6  lea     rax, [rsp+3BD0h+var_3BA0]
0x180012aeb  mov     [rsp+3BD0h+ResultLength], rax; ResultLength
0x180012af0  mov     [rsp+3BD0h+Length], r13d; Length
0x180012af5  lea     r9, [rbp+3AD0h+KeyInformation]; KeyValueInformation
0x180012afc  mov     r8d, ebx; KeyValueInformationClass
0x180012aff  lea     rdx, stru_1800163B8; ValueName
0x180012b06  mov     rcx, [rsp+3BD0h+Handle]; KeyHandle
0x180012b0b  call    cs:__imp_NtQueryValueKey
0x180012b11  mov     esi, eax
0x180012b13  test    eax, eax
0x180012b15  js      loc_180012C21
0x180012b1b  cmp     [rbp+3AD0h+var_207C], 1
0x180012b22  jnz     loc_180012C21
0x180012b28  mov     edx, [rbp+3AD0h+var_2078]
0x180012b2e  cmp     edx, 0FFFEh
0x180012b34  ja      loc_180012C21
0x180012b3a  movzx   eax, dx
0x180012b3d  sub     ax, bx
0x180012b40  movzx   ecx, ax
0x180012b43  mov     word ptr [rbp+3AD0h+var_3B40], cx
0x180012b47  mov     word ptr [rbp+3AD0h+var_3B40+2], dx
0x180012b4b  lea     rdx, [rbp+3AD0h+var_2074]
0x180012b52  mov     qword ptr [rbp+3AD0h+var_3B40+8], rdx
0x180012b56  mov     eax, ecx
0x180012b58  shr     rax, 1
0x180012b5b  cmp     word ptr [rbp+rax*2+3AD0h+var_2074], r12w
0x180012b64  jz      short loc_180012B8F
0x180012b66  cmp     [rsp+3BD0h+var_3BA0], r13d
0x180012b6b  jz      loc_180012C24
0x180012b71  add     cx, bx
0x180012b74  movzx   ecx, cx
0x180012b77  mov     word ptr [rbp+3AD0h+var_3B40], cx
0x180012b7b  shr     rcx, 1
0x180012b7e  mov     word ptr [rbp+rcx*2+3AD0h+var_2074], r12w
0x180012b87  add     word ptr [rbp+3AD0h+var_3B40+2], bx
0x180012b8b  mov     rdx, qword ptr [rbp+3AD0h+var_3B40+8]
0x180012b8f  lea     rcx, [rbp+3AD0h+var_3B20]
0x180012b93  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180012b98  nop
0x180012b99  mov     rdx, rax
0x180012b9c  lea     rcx, [rbp+3AD0h+var_2DC0]
0x180012ba3  call    ??0ImagePolicy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MitigationOptionsPolicy::ImagePolicy::ImagePolicy(std::wstring const &)
0x180012ba8  nop
0x180012ba9  lea     rcx, [rbp+3AD0h+var_3B20]
0x180012bad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012bb2  lea     rcx, [rbp+3AD0h+var_2DC0]; this
0x180012bb9  call    ?Load@ImagePolicy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::ImagePolicy::Load(void)
0x180012bbe  test    al, al
0x180012bc0  jz      short loc_180012C13
0x180012bc2  mov     ecx, 0C0000034h; Status
0x180012bc7  call    cs:__imp_RtlNtStatusToDosError
0x180012bcd  mov     ebx, eax
0x180012bcf  call    cs:__imp_GetLastError
0x180012bd5  cmp     eax, ebx
0x180012bd7  jz      short loc_180012C0E
0x180012bd9  mov     rax, [rdi+8]
0x180012bdd  cmp     rax, [rdi+10h]
0x180012be1  jz      short loc_180012BFC
0x180012be3  lea     rdx, [rbp+3AD0h+var_2DC0]; struct MitigationOptionsPolicy::ImagePolicy *
0x180012bea  mov     rcx, rax; this
0x180012bed  call    ??0ImagePolicy@MitigationOptionsPolicy@@QEAA@AEBV01@@Z; MitigationOptionsPolicy::ImagePolicy::ImagePolicy(MitigationOptionsPolicy::ImagePolicy const &)
0x180012bf2  add     qword ptr [rdi+8], 0D40h
0x180012bfa  jmp     short loc_180012C0E
0x180012bfc  lea     r8, [rbp+3AD0h+var_2DC0]
0x180012c03  mov     rdx, rax
0x180012c06  mov     rcx, rdi
0x180012c09  call    ??$_Emplace_reallocate@AEBVImagePolicy@MitigationOptionsPolicy@@@?$vector@VImagePolicy@MitigationOptionsPolicy@@V?$allocator@VImagePolicy@MitigationOptionsPolicy@@@std@@@std@@AEAAPEAVImagePolicy@MitigationOptionsPolicy@@QEAV23@AEBV23@@Z; std::vector<MitigationOptionsPolicy::ImagePolicy>::_Emplace_reallocate<MitigationOptionsPolicy::ImagePolicy const &>(MitigationOptionsPolicy::ImagePolicy * const,MitigationOptionsPolicy::ImagePolicy const &)
0x180012c0e  mov     ebx, 2
0x180012c13  lea     rcx, [rbp+3AD0h+var_2DC0]; this
0x180012c1a  call    ??1ImagePolicy@MitigationOptionsPolicy@@QEAA@XZ; MitigationOptionsPolicy::ImagePolicy::~ImagePolicy(void)
0x180012c1f  jmp     short loc_180012C24
0x180012c21  mov     esi, r12d
0x180012c24  mov     rcx, [rsp+3BD0h+Handle]; Handle
0x180012c29  test    rcx, rcx
0x180012c2c  jz      short loc_180012C34
0x180012c2e  call    cs:__imp_NtClose
0x180012c34  inc     r14d
0x180012c37  test    esi, esi
0x180012c39  jns     loc_180012A2C
0x180012c3f  mov     ebx, r12d
0x180012c42  lea     rcx, [rbp+3AD0h+var_3B00]; this
0x180012c46  call    ??1ImagePolicy@MitigationOptionsPolicy@@QEAA@XZ; MitigationOptionsPolicy::ImagePolicy::~ImagePolicy(void)
0x180012c4b  nop
0x180012c4c  mov     rcx, [rsp+3BD0h+var_3B98]; Handle
0x180012c51  test    rcx, rcx
0x180012c54  jz      short loc_180012C5C
0x180012c56  call    cs:__imp_NtClose
0x180012c5c  inc     r15d
0x180012c5f  test    ebx, ebx
0x180012c61  jns     loc_180012894
0x180012c67  cmp     ebx, 8000001Ah
0x180012c6d  jz      short loc_180012C94
0x180012c6f  mov     ecx, ebx; Status
0x180012c71  call    cs:__imp_RtlNtStatusToDosError
0x180012c77  mov     ecx, eax; dwErrCode
0x180012c79  call    cs:__imp_SetLastError
0x180012c7f  nop
0x180012c80  mov     rcx, [rsp+3BD0h+KeyHandle]; Handle
0x180012c85  test    rcx, rcx
0x180012c88  jz      short loc_180012C90
0x180012c8a  call    cs:__imp_NtClose
0x180012c90  xor     al, al
0x180012c92  jmp     short loc_180012CA6
0x180012c94  mov     rcx, [rsp+3BD0h+KeyHandle]; Handle
0x180012c99  test    rcx, rcx
0x180012c9c  jz      short loc_180012CA4
0x180012c9e  call    cs:__imp_NtClose
0x180012ca4  mov     al, 1
0x180012ca6  mov     rcx, [rbp+3AD0h+var_50]
0x180012cad  xor     rcx, rsp; StackCookie
0x180012cb0  call    __security_check_cookie
0x180012cb5  add     rsp, 3B98h
0x180012cbc  pop     r15
0x180012cbe  pop     r14
0x180012cc0  pop     r13
0x180012cc2  pop     r12
  ... truncated ...
```
