# CodeAuthzpOpenPolicyRootKey

- ea: `0x1800134c4`
- end: `0x180013940`
- name: `CodeAuthzpOpenPolicyRootKey`
- size: `1148`
- prototype: `__int64 __fastcall(int, void *, const WCHAR *, ACCESS_MASK, char, HANDLE *KeyHandle)`
- caller_count: `16`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800124e8`
- `0x180012758`
- `0x180012a60`
- `0x180013948`
- `0x180013bbc`
- `0x180014fe4`
- `0x18004aa98`
- `0x18004b768`
- `0x18004bd04`
- `0x18004be4c`
- `0x18004c398`
- `0x18004c674`
- `0x18004ddb4`
- `0x18004df58`
- `0x18004e104`
- `0x18004e29c`

## callees

- `0x1800134c4`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800135da`
- `ntdll!NtOpenKey` at `0x1800135da`
- `ntdll!NtClose` at `0x1800138d7`
- `ntdll!NtClose` at `0x1800138d7`
- `ntdll!NtCreateKey` at `0x180013846`
- `ntdll!NtCreateKey` at `0x1800138c0`
- `ntdll!NtCreateKey` at `0x18001392f`
- `ntdll!NtCreateKey` at `0x180013846`
- `ntdll!NtCreateKey` at `0x1800138c0`
- `ntdll!NtCreateKey` at `0x18001392f`
- `ntdll!RtlAppendUnicodeToString` at `0x180013583`
- `ntdll!RtlAppendUnicodeToString` at `0x18001369f`
- `ntdll!RtlAppendUnicodeToString` at `0x1800136bd`
- `ntdll!RtlAppendUnicodeToString` at `0x180013754`
- `ntdll!RtlAppendUnicodeToString` at `0x180013583`
- `ntdll!RtlAppendUnicodeToString` at `0x18001369f`
- `ntdll!RtlAppendUnicodeToString` at `0x1800136bd`
- `ntdll!RtlAppendUnicodeToString` at `0x180013754`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180013721`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180013721`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800136ee`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800136ee`
- `ntdll!RtlFreeHeap` at `0x180013670`
- `ntdll!RtlFreeHeap` at `0x180013670`
- `ntdll!RtlFreeUnicodeString` at `0x180013734`
- `ntdll!RtlFreeUnicodeString` at `0x180013734`
- `ntdll!RtlAllocateHeap` at `0x180013632`
- `ntdll!RtlAllocateHeap` at `0x180013782`
- `ntdll!RtlAllocateHeap` at `0x1800137e5`
- `ntdll!RtlAllocateHeap` at `0x180013632`
- `ntdll!RtlAllocateHeap` at `0x180013782`
- `ntdll!RtlAllocateHeap` at `0x1800137e5`

## string_xrefs

- `0x180013577`: `\Registry\Machine\Software\Policies\Microsoft\Windows\Safer`

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
0x1800134c4  mov     [rsp-8+arg_0], rbx
0x1800134c9  push    rbp
0x1800134ca  push    rsi
0x1800134cb  push    rdi
0x1800134cc  push    r12
0x1800134ce  push    r13
0x1800134d0  push    r14
0x1800134d2  push    r15
0x1800134d4  lea     rbp, [rsp-1C0h]
0x1800134dc  sub     rsp, 2C0h
0x1800134e3  mov     rax, cs:__security_cookie
0x1800134ea  xor     rax, rsp
0x1800134ed  mov     [rbp+1F0h+var_40], rax
0x1800134f4  mov     r12, [rbp+1F0h+KeyHandle]
0x1800134fb  xorps   xmm0, xmm0
0x1800134fe  xor     r13d, r13d
0x180013501  mov     [rbp+1F0h+var_260], r12
0x180013505  xor     eax, eax
0x180013507  mov     dword ptr [rsp+2F0h+Destination+4], r13d
0x18001350c  mov     r15d, r9d
0x18001350f  mov     rsi, r8
0x180013512  mov     r14, rdx
0x180013515  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm0
0x18001351a  movups  xmmword ptr [rsp+2F0h+ObjectAttributes+1Ch], xmm0
0x18001351f  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm0
0x180013524  test    r12, r12
0x180013527  jz      loc_1800137B5
0x18001352d  lea     edx, [rax+1]
0x180013530  mov     edi, r13d
0x180013533  test    r8, r8
0x180013536  jz      short loc_18001354C
0x180013538  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001353c  inc     rdi
0x18001353f  cmp     [r8+rdi*2], r13w
0x180013544  jnz     short loc_18001353C
0x180013546  add     di, dx
0x180013549  add     di, di
0x18001354c  mov     dword ptr [rsp+2F0h+Destination.Length], 2080000h
0x180013554  lea     rax, [rbp+1F0h+var_250]
0x180013558  mov     [rsp+2F0h+Destination.Buffer], rax
0x18001355d  mov     eax, 208h
0x180013562  cmp     ecx, edx
0x180013564  jnz     loc_1800136D8
0x18001356a  add     di, 7Ch ; '|'
0x18001356e  cmp     ax, di
0x180013571  jb      loc_18001361F
0x180013577  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\Software\\Policies"...
0x18001357e  lea     rcx, [rsp+2F0h+Destination]; Destination
0x180013583  call    cs:__imp_RtlAppendUnicodeToString
0x18001358a  nop     dword ptr [rax+rax+00h]
0x18001358f  mov     r14, r13
0x180013592  test    rsi, rsi
0x180013595  jnz     loc_180013681
0x18001359b  lea     rax, [rsp+2F0h+Destination]
0x1800135a0  xorps   xmm0, xmm0
0x1800135a3  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x1800135a8  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x1800135ad  mov     edx, r15d; DesiredAccess
0x1800135b0  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x1800135b8  mov     rcx, r12; KeyHandle
0x1800135bb  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], r14
0x1800135c0  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800135c5  mov     [rsp+2F0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800135cd  cmp     [rbp+1F0h+arg_20], r13b
0x1800135d4  jnz     loc_18001382F
0x1800135da  call    cs:__imp_NtOpenKey
0x1800135e1  nop     dword ptr [rax+rax+00h]
0x1800135e6  mov     ebx, eax
0x1800135e8  mov     rax, [rsp+2F0h+Destination.Buffer]
0x1800135ed  test    rax, rax
0x1800135f0  jnz     short loc_180013653
0x1800135f2  mov     eax, ebx
0x1800135f4  mov     rcx, [rbp+1F0h+var_40]
0x1800135fb  xor     rcx, rsp; StackCookie
0x1800135fe  call    __security_check_cookie
0x180013603  mov     rbx, [rsp+2F0h+arg_0]
0x18001360b  add     rsp, 2C0h
0x180013612  pop     r15
0x180013614  pop     r14
0x180013616  pop     r13
0x180013618  pop     r12
0x18001361a  pop     rdi
0x18001361b  pop     rsi
0x18001361c  pop     rbp
0x18001361d  retn
0x18001361f  mov     rcx, gs:60h
0x180013628  xor     edx, edx; Flags
0x18001362a  movzx   r8d, di; Size
0x18001362e  mov     rcx, [rcx+30h]; HeapHandle
0x180013632  call    cs:__imp_RtlAllocateHeap
0x180013639  nop     dword ptr [rax+rax+00h]
0x18001363e  mov     [rsp+2F0h+Destination.Buffer], rax
0x180013643  test    rax, rax
0x180013646  jnz     loc_1800137BF
0x18001364c  mov     eax, 0C0000017h
0x180013651  jmp     short loc_1800135F4
0x180013653  lea     rcx, [rbp+1F0h+var_250]
0x180013657  cmp     rax, rcx
0x18001365a  jz      short loc_1800135F2
0x18001365c  mov     rcx, gs:60h
0x180013665  xor     edx, edx; Flags
0x180013667  mov     r8, [rsp+2F0h+Destination.Buffer]; P
0x18001366c  mov     rcx, [rcx+30h]; HeapHandle
0x180013670  call    cs:__imp_RtlFreeHeap
0x180013677  nop     dword ptr [rax+rax+00h]
0x18001367c  jmp     loc_1800135F2
0x180013681  cmp     [rsp+2F0h+Destination.Length], r13w
0x180013687  jbe     loc_180013809
0x18001368d  cmp     word ptr [rsi], 5Ch ; '\'
0x180013691  jz      short loc_1800136B5
0x180013693  lea     rdx, asc_1800888C8; "\\"
0x18001369a  lea     rcx, [rsp+2F0h+Destination]; Destination
0x18001369f  call    cs:__imp_RtlAppendUnicodeToString
0x1800136a6  nop     dword ptr [rax+rax+00h]
0x1800136ab  mov     ebx, eax
0x1800136ad  test    eax, eax
0x1800136af  js      loc_1800135E8
0x1800136b5  mov     rdx, rsi; Source
0x1800136b8  lea     rcx, [rsp+2F0h+Destination]; Destination
0x1800136bd  call    cs:__imp_RtlAppendUnicodeToString
0x1800136c4  nop     dword ptr [rax+rax+00h]
0x1800136c9  mov     ebx, eax
0x1800136cb  test    eax, eax
0x1800136cd  jns     loc_18001359B
0x1800136d3  jmp     loc_1800135E8
0x1800136d8  cmp     ecx, 2
0x1800136db  jnz     loc_1800137A6
0x1800136e1  xorps   xmm0, xmm0
0x1800136e4  lea     rcx, [rsp+2F0h+KeyPath]; KeyPath
0x1800136e9  movups  xmmword ptr [rsp+2F0h+KeyPath.Length], xmm0
0x1800136ee  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x1800136f5  nop     dword ptr [rax+rax+00h]
0x1800136fa  mov     ebx, eax
0x1800136fc  test    eax, eax
0x1800136fe  js      loc_1800135E8
0x180013704  movzx   ebx, [rsp+2F0h+KeyPath.Length]
0x180013709  add     bx, 56h ; 'V'
0x18001370d  add     bx, di
0x180013710  cmp     [rsp+2F0h+Destination.MaximumLength], bx
0x180013715  jb      short loc_18001376F
0x180013717  lea     rdx, [rsp+2F0h+KeyPath]; Source
0x18001371c  lea     rcx, [rsp+2F0h+Destination]; Destination
0x180013721  call    cs:__imp_RtlAppendUnicodeStringToString
0x180013728  nop     dword ptr [rax+rax+00h]
0x18001372d  lea     rcx, [rsp+2F0h+KeyPath]; UnicodeString
0x180013732  mov     ebx, eax
0x180013734  call    cs:__imp_RtlFreeUnicodeString
0x18001373b  nop     dword ptr [rax+rax+00h]
0x180013740  test    ebx, ebx
0x180013742  js      loc_1800135E8
0x180013748  lea     rdx, aSoftwarePolici; "\\Software\\Policies\\Microsoft\\Window"...
0x18001374f  lea     rcx, [rsp+2F0h+Destination]; Destination
0x180013754  call    cs:__imp_RtlAppendUnicodeToString
0x18001375b  nop     dword ptr [rax+rax+00h]
0x180013760  mov     ebx, eax
0x180013762  test    eax, eax
0x180013764  js      loc_1800135E8
0x18001376a  jmp     loc_18001358F
0x18001376f  mov     rcx, gs:60h
0x180013778  xor     edx, edx; Flags
0x18001377a  movzx   r8d, bx; Size
0x18001377e  mov     rcx, [rcx+30h]; HeapHandle
0x180013782  call    cs:__imp_RtlAllocateHeap
0x180013789  nop     dword ptr [rax+rax+00h]
0x18001378e  mov     [rsp+2F0h+Destination.Buffer], rax
0x180013793  test    rax, rax
0x180013796  jz      loc_18001364C
0x18001379c  mov     [rsp+2F0h+Destination.MaximumLength], bx
0x1800137a1  jmp     loc_180013717
0x1800137a6  cmp     ecx, 3
0x1800137a9  jz      short loc_1800137C9
0x1800137ab  mov     eax, 0C00000EFh
0x1800137b0  jmp     loc_1800135F4
0x1800137b5  mov     eax, 0C00000F2h
0x1800137ba  jmp     loc_1800135F4
0x1800137bf  mov     [rsp+2F0h+Destination.MaximumLength], di
0x1800137c4  jmp     loc_180013577
0x1800137c9  cmp     ax, di
0x1800137cc  jnb     loc_180013592
0x1800137d2  mov     rcx, gs:60h
0x1800137db  xor     edx, edx; Flags
0x1800137dd  movzx   r8d, di; Size
0x1800137e1  mov     rcx, [rcx+30h]; HeapHandle
0x1800137e5  call    cs:__imp_RtlAllocateHeap
0x1800137ec  nop     dword ptr [rax+rax+00h]
0x1800137f1  mov     [rsp+2F0h+Destination.Buffer], rax
0x1800137f6  test    rax, rax
0x1800137f9  jz      loc_18001364C
0x1800137ff  mov     [rsp+2F0h+Destination.MaximumLength], di
0x180013804  jmp     loc_180013592
0x180013809  test    r14, r14
0x18001380c  jz      loc_1800136B5
0x180013812  jmp     short loc_180013822
0x180013814  cmp     ax, 5Ch ; '\'
0x180013818  jnz     loc_1800136B5
0x18001381e  add     rsi, 2
0x180013822  movzx   eax, word ptr [rsi]
0x180013825  test    ax, ax
0x180013828  jnz     short loc_180013814
0x18001382a  jmp     loc_1800136B5
0x18001382f  mov     eax, cs:g_dwKeyOptions
0x180013835  xor     r9d, r9d; TitleIndex
0x180013838  mov     [rsp+2F0h+Disposition], r13; Disposition
0x18001383d  mov     [rsp+2F0h+CreateOptions], eax; CreateOptions
0x180013841  mov     [rsp+2F0h+Class], r13; Class
0x180013846  call    cs:__imp_NtCreateKey
0x18001384d  nop     dword ptr [rax+rax+00h]
0x180013852  mov     ebx, eax
0x180013854  cmp     eax, 0C0000034h
0x180013859  jnz     loc_1800135E8
0x18001385f  movzx   edi, [rsp+2F0h+Destination.Length]
0x180013864  mov     r14b, r13b
0x180013867  shr     di, 1
0x18001386a  mov     esi, r13d
0x18001386d  cmp     r13w, di
0x180013871  jnb     loc_1800135E8
0x180013877  mov     r12d, 1
0x18001387d  mov     rax, [rsp+2F0h+Destination.Buffer]
0x180013882  movzx   ecx, si
0x180013885  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x18001388a  jnz     short loc_1800138EF
0x18001388c  movzx   eax, si
0x18001388f  mov     [rsp+2F0h+Disposition], r13; Disposition
0x180013894  add     ax, ax
0x180013897  mov     qword ptr [rsp+2F0h+KeyPath.Length], r13
0x18001389c  mov     [rsp+2F0h+Destination.Length], ax
0x1800138a1  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x1800138a6  mov     eax, cs:g_dwKeyOptions
0x1800138ac  lea     rcx, [rsp+2F0h+KeyPath]; KeyHandle
0x1800138b1  mov     [rsp+2F0h+CreateOptions], eax; CreateOptions
0x1800138b5  xor     r9d, r9d; TitleIndex
0x1800138b8  mov     edx, r15d; DesiredAccess
0x1800138bb  mov     [rsp+2F0h+Class], r13; Class
0x1800138c0  call    cs:__imp_NtCreateKey
0x1800138c7  nop     dword ptr [rax+rax+00h]
0x1800138cc  mov     ebx, eax
0x1800138ce  test    eax, eax
0x1800138d0  js      short loc_1800138E5
0x1800138d2  mov     rcx, qword ptr [rsp+2F0h+KeyPath.Length]; Handle
0x1800138d7  call    cs:__imp_NtClose
0x1800138de  nop     dword ptr [rax+rax+00h]
0x1800138e3  jmp     short loc_1800138EC
0x1800138e5  cmp     eax, 0C0000034h
0x1800138ea  jz      short loc_1800138F8
0x1800138ec  mov     r14b, r12b
0x1800138ef  add     si, r12w
0x1800138f3  cmp     si, di
0x1800138f6  jb      short loc_18001387D
0x1800138f8  mov     r12, [rbp+1F0h+var_260]
0x1800138fc  test    r14b, r14b
0x1800138ff  jz      loc_1800135E8
0x180013905  mov     eax, cs:g_dwKeyOptions
0x18001390b  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x180013910  add     di, di
0x180013913  mov     [rsp+2F0h+Disposition], r13; Disposition
0x180013918  mov     [rsp+2F0h+CreateOptions], eax; CreateOptions
0x18001391c  xor     r9d, r9d; TitleIndex
0x18001391f  mov     edx, r15d; DesiredAccess
0x180013922  mov     [rsp+2F0h+Destination.Length], di
0x180013927  mov     rcx, r12; KeyHandle
0x18001392a  mov     [rsp+2F0h+Class], r13; Class
0x18001392f  call    cs:__imp_NtCreateKey
0x180013936  nop     dword ptr [rax+rax+00h]
0x18001393b  jmp     loc_1800135E6
```
