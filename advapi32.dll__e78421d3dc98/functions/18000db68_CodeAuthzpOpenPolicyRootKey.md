# CodeAuthzpOpenPolicyRootKey

- ea: `0x18000db68`
- end: `0x18000df7d`
- name: `CodeAuthzpOpenPolicyRootKey`
- size: `1045`
- prototype: `__int64 __fastcall(int, void *, const WCHAR *, ACCESS_MASK, char, HANDLE *KeyHandle)`
- caller_count: `16`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ccf4`
- `0x18000cf3c`
- `0x18000d20c`
- `0x18000df84`
- `0x18000e1d0`
- `0x18000f494`
- `0x18004535c`
- `0x180045f64`
- `0x180046530`
- `0x18004666c`
- `0x180046b50`
- `0x180046de8`
- `0x1800482d0`
- `0x18004844c`
- `0x1800485d4`
- `0x18004874c`

## callees

- `0x18000db68`
- `0x180065090`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18000dc78`
- `ntdll!NtOpenKey` at `0x18000dc78`
- `ntdll!NtClose` at `0x18000df20`
- `ntdll!NtClose` at `0x18000df20`
- `ntdll!NtCreateKey` at `0x18000de9b`
- `ntdll!NtCreateKey` at `0x18000df0f`
- `ntdll!NtCreateKey` at `0x18000df72`
- `ntdll!NtCreateKey` at `0x18000de9b`
- `ntdll!NtCreateKey` at `0x18000df0f`
- `ntdll!NtCreateKey` at `0x18000df72`
- `ntdll!RtlAppendUnicodeToString` at `0x18000dc27`
- `ntdll!RtlAppendUnicodeToString` at `0x18000dd27`
- `ntdll!RtlAppendUnicodeToString` at `0x18000dd3f`
- `ntdll!RtlAppendUnicodeToString` at `0x18000ddbe`
- `ntdll!RtlAppendUnicodeToString` at `0x18000dc27`
- `ntdll!RtlAppendUnicodeToString` at `0x18000dd27`
- `ntdll!RtlAppendUnicodeToString` at `0x18000dd3f`
- `ntdll!RtlAppendUnicodeToString` at `0x18000ddbe`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000dd97`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000dd97`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18000dd6a`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18000dd6a`
- `ntdll!RtlFreeHeap` at `0x18000dd01`
- `ntdll!RtlFreeHeap` at `0x18000dd01`
- `ntdll!RtlFreeUnicodeString` at `0x18000dda4`
- `ntdll!RtlFreeUnicodeString` at `0x18000dda4`
- `ntdll!RtlAllocateHeap` at `0x18000dcc9`
- `ntdll!RtlAllocateHeap` at `0x18000dde6`
- `ntdll!RtlAllocateHeap` at `0x18000de40`
- `ntdll!RtlAllocateHeap` at `0x18000dcc9`
- `ntdll!RtlAllocateHeap` at `0x18000dde6`
- `ntdll!RtlAllocateHeap` at `0x18000de40`

## string_xrefs

- `0x18000dc1b`: `\Registry\Machine\Software\Policies\Microsoft\Windows\Safer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CodeAuthzpOpenPolicyRootKey(
        int a1,
        void *a2,
        const WCHAR *a3,
        ACCESS_MASK a4,
        char a5,
        HANDLE *KeyHandle)
{
  const WCHAR *v7; // rsi
  USHORT v9; // di
  __int64 v10; // rdi
  USHORT v11; // di
  NTSTATUS v12; // eax
  NTSTATUS appended; // ebx
  USHORT v15; // bx
  char v16; // r14
  unsigned __int16 v17; // di
  unsigned __int16 v18; // si
  NTSTATUS v19; // eax
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  PHANDLE v23; // [rsp+90h] [rbp-70h]
  _BYTE v24[528]; // [rsp+A0h] [rbp-60h] BYREF

  v23 = KeyHandle;
  *(_DWORD *)(&Destination.MaximumLength + 1) = 0;
  v7 = a3;
  memset(&ObjectAttributes, 0, 44);
  if ( !KeyHandle )
    return 3221225714LL;
  v9 = 0;
  if ( a3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    v9 = 2 * (v10 + 1);
  }
  *(_DWORD *)&Destination.Length = 34078720;
  Destination.Buffer = (PWSTR)v24;
  if ( a1 != 1 )
  {
    if ( a1 == 2 )
    {
      KeyPath = 0;
      appended = RtlFormatCurrentUserKeyPath(&KeyPath);
      if ( appended < 0 )
        goto LABEL_14;
      v15 = v9 + KeyPath.Length + 86;
      if ( Destination.MaximumLength < v15 )
      {
        Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
        if ( !Destination.Buffer )
          return 3221225495LL;
        Destination.MaximumLength = v15;
      }
      appended = RtlAppendUnicodeStringToString(&Destination, &KeyPath);
      RtlFreeUnicodeString(&KeyPath);
      if ( appended < 0 )
        goto LABEL_14;
      appended = RtlAppendUnicodeToString(&Destination, L"\\Software\\Policies\\Microsoft\\Windows\\Safer");
      if ( appended < 0 )
        goto LABEL_14;
      goto LABEL_9;
    }
    if ( a1 != 3 )
      return 3221225711LL;
    if ( v9 <= 0x208u )
      goto LABEL_10;
    Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    if ( Destination.Buffer )
    {
      Destination.MaximumLength = v9;
      goto LABEL_10;
    }
    return 3221225495LL;
  }
  v11 = v9 + 124;
  if ( v11 > 0x208u )
  {
    Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    if ( Destination.Buffer )
    {
      Destination.MaximumLength = v11;
      goto LABEL_8;
    }
    return 3221225495LL;
  }
LABEL_8:
  RtlAppendUnicodeToString(&Destination, L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\Safer");
LABEL_9:
  a2 = 0;
LABEL_10:
  if ( !v7 )
    goto LABEL_11;
  if ( Destination.Length )
  {
    if ( *v7 != 92 )
    {
      appended = RtlAppendUnicodeToString(&Destination, L"\\");
      if ( appended < 0 )
        goto LABEL_14;
    }
  }
  else if ( a2 )
  {
    while ( *v7 == 92 )
      ++v7;
  }
  appended = RtlAppendUnicodeToString(&Destination, v7);
  if ( appended >= 0 )
  {
LABEL_11:
    ObjectAttributes.ObjectName = &Destination;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = a2;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.Attributes = 64;
    if ( a5 )
    {
      appended = NtCreateKey(KeyHandle, a4, &ObjectAttributes, 0, 0, g_dwKeyOptions, 0);
      if ( appended != -1073741772 )
        goto LABEL_14;
      v16 = 0;
      v17 = Destination.Length >> 1;
      v18 = 0;
      if ( !(Destination.Length >> 1) )
        goto LABEL_14;
      do
      {
        if ( Destination.Buffer[v18] == 92 )
        {
          *(_QWORD *)&KeyPath.Length = 0;
          Destination.Length = 2 * v18;
          v19 = NtCreateKey((PHANDLE)&KeyPath, a4, &ObjectAttributes, 0, 0, g_dwKeyOptions, 0);
          appended = v19;
          if ( v19 < 0 )
          {
            if ( v19 == -1073741772 )
              break;
          }
          else
          {
            NtClose(*(HANDLE *)&KeyPath.Length);
          }
          v16 = 1;
        }
        ++v18;
      }
      while ( v18 < v17 );
      if ( !v16 )
        goto LABEL_14;
      Destination.Length = 2 * v17;
      v12 = NtCreateKey(v23, a4, &ObjectAttributes, 0, 0, g_dwKeyOptions, 0);
    }
    else
    {
      v12 = NtOpenKey(KeyHandle, a4, &ObjectAttributes);
    }
    appended = v12;
  }
LABEL_14:
  if ( Destination.Buffer )
  {
    if ( (_BYTE *)Destination.Buffer != v24 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18000db68  mov     [rsp-8+arg_0], rbx
0x18000db6d  push    rbp
0x18000db6e  push    rsi
0x18000db6f  push    rdi
0x18000db70  push    r12
0x18000db72  push    r13
0x18000db74  push    r14
0x18000db76  push    r15
0x18000db78  lea     rbp, [rsp-1C0h]
0x18000db80  sub     rsp, 2C0h
0x18000db87  mov     rax, cs:__security_cookie
0x18000db8e  xor     rax, rsp
0x18000db91  mov     [rbp+1F0h+var_40], rax
0x18000db98  mov     r12, [rbp+1F0h+KeyHandle]
0x18000db9f  xorps   xmm0, xmm0
0x18000dba2  xor     r13d, r13d
0x18000dba5  mov     [rbp+1F0h+var_260], r12
0x18000dba9  xor     eax, eax
0x18000dbab  mov     dword ptr [rsp+2F0h+Destination+4], r13d
0x18000dbb0  mov     r15d, r9d
0x18000dbb3  mov     rsi, r8
0x18000dbb6  mov     r14, rdx
0x18000dbb9  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm0
0x18000dbbe  movups  xmmword ptr [rsp+2F0h+ObjectAttributes+1Ch], xmm0
0x18000dbc3  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm0
0x18000dbc8  test    r12, r12
0x18000dbcb  jz      loc_18000DE10
0x18000dbd1  lea     edx, [rax+1]
0x18000dbd4  mov     edi, r13d
0x18000dbd7  test    r8, r8
0x18000dbda  jz      short loc_18000DBF0
0x18000dbdc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000dbe0  inc     rdi
0x18000dbe3  cmp     [r8+rdi*2], r13w
0x18000dbe8  jnz     short loc_18000DBE0
0x18000dbea  add     di, dx
0x18000dbed  add     di, di
0x18000dbf0  mov     dword ptr [rsp+2F0h+Destination.Length], 2080000h
0x18000dbf8  lea     rax, [rbp+1F0h+var_250]
0x18000dbfc  mov     [rsp+2F0h+Destination.Buffer], rax
0x18000dc01  mov     eax, 208h
0x18000dc06  cmp     ecx, edx
0x18000dc08  jnz     loc_18000DD54
0x18000dc0e  add     di, 7Ch ; '|'
0x18000dc12  cmp     ax, di
0x18000dc15  jb      loc_18000DCB6
0x18000dc1b  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\Software\\Policies"...
0x18000dc22  lea     rcx, [rsp+2F0h+Destination]; Destination
0x18000dc27  call    cs:__imp_RtlAppendUnicodeToString
0x18000dc2d  mov     r14, r13
0x18000dc30  test    rsi, rsi
0x18000dc33  jnz     loc_18000DD09
0x18000dc39  lea     rax, [rsp+2F0h+Destination]
0x18000dc3e  xorps   xmm0, xmm0
0x18000dc41  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18000dc46  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x18000dc4b  mov     edx, r15d; DesiredAccess
0x18000dc4e  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x18000dc56  mov     rcx, r12; KeyHandle
0x18000dc59  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], r14
0x18000dc5e  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000dc63  mov     [rsp+2F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000dc6b  cmp     [rbp+1F0h+arg_20], r13b
0x18000dc72  jnz     loc_18000DE84
0x18000dc78  call    cs:__imp_NtOpenKey
0x18000dc7e  mov     ebx, eax
0x18000dc80  mov     rax, [rsp+2F0h+Destination.Buffer]
0x18000dc85  test    rax, rax
0x18000dc88  jnz     short loc_18000DCE4
0x18000dc8a  mov     eax, ebx
0x18000dc8c  mov     rcx, [rbp+1F0h+var_40]
0x18000dc93  xor     rcx, rsp; StackCookie
0x18000dc96  call    __security_check_cookie
0x18000dc9b  mov     rbx, [rsp+2F0h+arg_0]
0x18000dca3  add     rsp, 2C0h
0x18000dcaa  pop     r15
0x18000dcac  pop     r14
0x18000dcae  pop     r13
0x18000dcb0  pop     r12
0x18000dcb2  pop     rdi
0x18000dcb3  pop     rsi
0x18000dcb4  pop     rbp
0x18000dcb5  retn
0x18000dcb6  mov     rcx, gs:60h
0x18000dcbf  xor     edx, edx; Flags
0x18000dcc1  movzx   r8d, di; Size
0x18000dcc5  mov     rcx, [rcx+30h]; HeapHandle
0x18000dcc9  call    cs:__imp_RtlAllocateHeap
0x18000dccf  mov     [rsp+2F0h+Destination.Buffer], rax
0x18000dcd4  test    rax, rax
0x18000dcd7  jnz     loc_18000DE1A
0x18000dcdd  mov     eax, 0C0000017h
0x18000dce2  jmp     short loc_18000DC8C
0x18000dce4  lea     rcx, [rbp+1F0h+var_250]
0x18000dce8  cmp     rax, rcx
0x18000dceb  jz      short loc_18000DC8A
0x18000dced  mov     rcx, gs:60h
0x18000dcf6  xor     edx, edx; Flags
0x18000dcf8  mov     r8, [rsp+2F0h+Destination.Buffer]; P
0x18000dcfd  mov     rcx, [rcx+30h]; HeapHandle
0x18000dd01  call    cs:__imp_RtlFreeHeap
0x18000dd07  jmp     short loc_18000DC8A
0x18000dd09  cmp     [rsp+2F0h+Destination.Length], r13w
0x18000dd0f  jbe     loc_18000DE5E
0x18000dd15  cmp     word ptr [rsi], 5Ch ; '\'
0x18000dd19  jz      short loc_18000DD37
0x18000dd1b  lea     rdx, asc_18007A738; "\\"
0x18000dd22  lea     rcx, [rsp+2F0h+Destination]; Destination
0x18000dd27  call    cs:__imp_RtlAppendUnicodeToString
0x18000dd2d  mov     ebx, eax
0x18000dd2f  test    eax, eax
0x18000dd31  js      loc_18000DC80
0x18000dd37  mov     rdx, rsi; Source
0x18000dd3a  lea     rcx, [rsp+2F0h+Destination]; Destination
0x18000dd3f  call    cs:__imp_RtlAppendUnicodeToString
0x18000dd45  mov     ebx, eax
0x18000dd47  test    eax, eax
0x18000dd49  jns     loc_18000DC39
0x18000dd4f  jmp     loc_18000DC80
0x18000dd54  cmp     ecx, 2
0x18000dd57  jnz     loc_18000DE01
0x18000dd5d  xorps   xmm0, xmm0
0x18000dd60  lea     rcx, [rsp+2F0h+KeyPath]; KeyPath
0x18000dd65  movups  xmmword ptr [rsp+2F0h+KeyPath.Length], xmm0
0x18000dd6a  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18000dd70  mov     ebx, eax
0x18000dd72  test    eax, eax
0x18000dd74  js      loc_18000DC80
0x18000dd7a  movzx   ebx, [rsp+2F0h+KeyPath.Length]
0x18000dd7f  add     bx, 56h ; 'V'
0x18000dd83  add     bx, di
0x18000dd86  cmp     [rsp+2F0h+Destination.MaximumLength], bx
0x18000dd8b  jb      short loc_18000DDD3
0x18000dd8d  lea     rdx, [rsp+2F0h+KeyPath]; Source
0x18000dd92  lea     rcx, [rsp+2F0h+Destination]; Destination
0x18000dd97  call    cs:__imp_RtlAppendUnicodeStringToString
0x18000dd9d  lea     rcx, [rsp+2F0h+KeyPath]; UnicodeString
0x18000dda2  mov     ebx, eax
0x18000dda4  call    cs:__imp_RtlFreeUnicodeString
0x18000ddaa  test    ebx, ebx
0x18000ddac  js      loc_18000DC80
0x18000ddb2  lea     rdx, aSoftwarePolici; "\\Software\\Policies\\Microsoft\\Window"...
0x18000ddb9  lea     rcx, [rsp+2F0h+Destination]; Destination
0x18000ddbe  call    cs:__imp_RtlAppendUnicodeToString
0x18000ddc4  mov     ebx, eax
0x18000ddc6  test    eax, eax
0x18000ddc8  js      loc_18000DC80
0x18000ddce  jmp     loc_18000DC2D
0x18000ddd3  mov     rcx, gs:60h
0x18000dddc  xor     edx, edx; Flags
0x18000ddde  movzx   r8d, bx; Size
0x18000dde2  mov     rcx, [rcx+30h]; HeapHandle
0x18000dde6  call    cs:__imp_RtlAllocateHeap
0x18000ddec  mov     [rsp+2F0h+Destination.Buffer], rax
0x18000ddf1  test    rax, rax
0x18000ddf4  jz      loc_18000DCDD
0x18000ddfa  mov     [rsp+2F0h+Destination.MaximumLength], bx
0x18000ddff  jmp     short loc_18000DD8D
0x18000de01  cmp     ecx, 3
0x18000de04  jz      short loc_18000DE24
0x18000de06  mov     eax, 0C00000EFh
0x18000de0b  jmp     loc_18000DC8C
0x18000de10  mov     eax, 0C00000F2h
0x18000de15  jmp     loc_18000DC8C
0x18000de1a  mov     [rsp+2F0h+Destination.MaximumLength], di
0x18000de1f  jmp     loc_18000DC1B
0x18000de24  cmp     ax, di
0x18000de27  jnb     loc_18000DC30
0x18000de2d  mov     rcx, gs:60h
0x18000de36  xor     edx, edx; Flags
0x18000de38  movzx   r8d, di; Size
0x18000de3c  mov     rcx, [rcx+30h]; HeapHandle
0x18000de40  call    cs:__imp_RtlAllocateHeap
0x18000de46  mov     [rsp+2F0h+Destination.Buffer], rax
0x18000de4b  test    rax, rax
0x18000de4e  jz      loc_18000DCDD
0x18000de54  mov     [rsp+2F0h+Destination.MaximumLength], di
0x18000de59  jmp     loc_18000DC30
0x18000de5e  test    r14, r14
0x18000de61  jz      loc_18000DD37
0x18000de67  jmp     short loc_18000DE77
0x18000de69  cmp     ax, 5Ch ; '\'
0x18000de6d  jnz     loc_18000DD37
0x18000de73  add     rsi, 2
0x18000de77  movzx   eax, word ptr [rsi]
0x18000de7a  test    ax, ax
0x18000de7d  jnz     short loc_18000DE69
0x18000de7f  jmp     loc_18000DD37
0x18000de84  mov     eax, cs:g_dwKeyOptions
0x18000de8a  xor     r9d, r9d; TitleIndex
0x18000de8d  mov     [rsp+2F0h+Disposition], r13; Disposition
0x18000de92  mov     [rsp+2F0h+CreateOptions], eax; CreateOptions
0x18000de96  mov     [rsp+2F0h+Class], r13; Class
0x18000de9b  call    cs:__imp_NtCreateKey
0x18000dea1  mov     ebx, eax
0x18000dea3  cmp     eax, 0C0000034h
0x18000dea8  jnz     loc_18000DC80
0x18000deae  movzx   edi, [rsp+2F0h+Destination.Length]
0x18000deb3  mov     r14b, r13b
0x18000deb6  shr     di, 1
0x18000deb9  mov     esi, r13d
0x18000debc  cmp     r13w, di
0x18000dec0  jnb     loc_18000DC80
0x18000dec6  mov     r12d, 1
0x18000decc  mov     rax, [rsp+2F0h+Destination.Buffer]
0x18000ded1  movzx   ecx, si
0x18000ded4  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x18000ded9  jnz     short loc_18000DF32
0x18000dedb  movzx   eax, si
0x18000dede  mov     [rsp+2F0h+Disposition], r13; Disposition
0x18000dee3  add     ax, ax
0x18000dee6  mov     qword ptr [rsp+2F0h+KeyPath.Length], r13
0x18000deeb  mov     [rsp+2F0h+Destination.Length], ax
0x18000def0  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18000def5  mov     eax, cs:g_dwKeyOptions
0x18000defb  lea     rcx, [rsp+2F0h+KeyPath]; KeyHandle
0x18000df00  mov     [rsp+2F0h+CreateOptions], eax; CreateOptions
0x18000df04  xor     r9d, r9d; TitleIndex
0x18000df07  mov     edx, r15d; DesiredAccess
0x18000df0a  mov     [rsp+2F0h+Class], r13; Class
0x18000df0f  call    cs:__imp_NtCreateKey
0x18000df15  mov     ebx, eax
0x18000df17  test    eax, eax
0x18000df19  js      short loc_18000DF28
0x18000df1b  mov     rcx, qword ptr [rsp+2F0h+KeyPath.Length]; Handle
0x18000df20  call    cs:__imp_NtClose
0x18000df26  jmp     short loc_18000DF2F
0x18000df28  cmp     eax, 0C0000034h
0x18000df2d  jz      short loc_18000DF3B
0x18000df2f  mov     r14b, r12b
0x18000df32  add     si, r12w
0x18000df36  cmp     si, di
0x18000df39  jb      short loc_18000DECC
0x18000df3b  mov     r12, [rbp+1F0h+var_260]
0x18000df3f  test    r14b, r14b
0x18000df42  jz      loc_18000DC80
0x18000df48  mov     eax, cs:g_dwKeyOptions
0x18000df4e  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18000df53  add     di, di
0x18000df56  mov     [rsp+2F0h+Disposition], r13; Disposition
0x18000df5b  mov     [rsp+2F0h+CreateOptions], eax; CreateOptions
0x18000df5f  xor     r9d, r9d; TitleIndex
0x18000df62  mov     edx, r15d; DesiredAccess
0x18000df65  mov     [rsp+2F0h+Destination.Length], di
0x18000df6a  mov     rcx, r12; KeyHandle
0x18000df6d  mov     [rsp+2F0h+Class], r13; Class
0x18000df72  call    cs:__imp_NtCreateKey
0x18000df78  jmp     loc_18000DC7E
```
