# UxOpenSubKeyByIndex

- ea: `0x14008ebac`
- end: `0x14008ee53`
- name: `UxOpenSubKeyByIndex`
- size: `679`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, ULONG Index@<edx>, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14008e440`
- `0x14008e980`
- `0x140135bb0`

## callees

- `0x14008ebac`
- `0x1400906ac`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14008ed65`
- `ntoskrnl!ZwOpenKey` at `0x14008ed65`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008ec1c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008ec1c`
- `ntoskrnl!ZwCreateKey` at `0x14008ec68`
- `ntoskrnl!ZwCreateKey` at `0x14008ec68`
- `ntoskrnl!ZwEnumerateKey` at `0x14008ece0`
- `ntoskrnl!ZwEnumerateKey` at `0x14008ece0`
- `ntoskrnl!ZwClose` at `0x14008edb6`
- `ntoskrnl!ZwClose` at `0x14008ee42`
- `ntoskrnl!ZwClose` at `0x14008edb6`
- `ntoskrnl!ZwClose` at `0x14008ee42`
- `ntoskrnl!ExAllocatePool3` at `0x14008ecab`
- `ntoskrnl!ExAllocatePool3` at `0x14008ecab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008eda1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008edd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ee0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008eda1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008edd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ee0c`

## pseudocode

```c
__int64 __fastcall UxOpenSubKeyByIndex(PCWSTR SourceString, ULONG Index, __int64 a3, PVOID *a4, HANDLE *a5)
{
  HANDLE *v5; // r15
  PVOID v7; // rsi
  _DWORD *v9; // rdi
  NTSTATUS WideString; // ebx
  _DWORD *Pool3; // rax
  NTSTATUS v12; // eax
  unsigned int v13; // eax
  HANDLE Handle; // [rsp+48h] [rbp-31h] BYREF
  PVOID P; // [rsp+50h] [rbp-29h]
  __int128 v17; // [rsp+58h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-1h] BYREF
  ULONG Length; // [rsp+E8h] [rbp+6Fh] BYREF
  void *KeyHandle; // [rsp+F0h] [rbp+77h] BYREF

  v5 = a5;
  KeyHandle = 0;
  Handle = 0;
  v7 = 0;
  *a4 = 0;
  *v5 = 0;
  P = 0;
  Length = 0;
  v9 = 0;
  DestinationString = 0;
  v17 = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  WideString = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( WideString >= 0 )
  {
    Length = 152;
    do
    {
      if ( v9 )
        ExFreePoolWithTag(v9, 0);
      Pool3 = (_DWORD *)ExAllocatePool3(258, Length, 1146252373, UxLowPriorityPool, 1);
      v9 = Pool3;
      if ( !Pool3 )
      {
        WideString = -1073741670;
        goto LABEL_16;
      }
      v12 = ZwEnumerateKey(KeyHandle, Index, KeyBasicInformation, Pool3, Length, &Length);
      WideString = v12;
    }
    while ( v12 == -2147483643 || v12 == -1073741789 );
    if ( v12 < 0 )
      goto LABEL_16;
    v13 = v9[3];
    if ( (v13 & 1) != 0 || v13 > 0xFFFE )
    {
      WideString = -1073741492;
    }
    else
    {
      *((_QWORD *)&v17 + 1) = v9 + 4;
      LOWORD(v17) = *((_WORD *)v9 + 6);
      WORD1(v17) = *((_WORD *)v9 + 6);
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v17;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      WideString = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
      if ( WideString < 0 )
        goto LABEL_16;
      WideString = UlAllocateWideString(v9 + 4);
      if ( WideString >= 0 )
      {
        *v5 = Handle;
        *a4 = P;
        Handle = 0;
        goto LABEL_16;
      }
      v7 = P;
    }
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
  }
LABEL_16:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  return (unsigned int)WideString;
}

```

## disassembly

```asm
0x14008ebac  mov     rax, rsp
0x14008ebaf  mov     [rax+8], rbx
0x14008ebb3  mov     [rax+10h], rsi
0x14008ebb7  mov     [rax+18h], r8b
0x14008ebbb  push    rbp
0x14008ebbc  push    rdi
0x14008ebbd  push    r12
0x14008ebbf  push    r14
0x14008ebc1  push    r15
0x14008ebc3  lea     rbp, [rax-57h]
0x14008ebc7  sub     rsp, 0A0h
0x14008ebce  mov     r15, [rbp+4Fh+arg_20]
0x14008ebd2  xorps   xmm0, xmm0
0x14008ebd5  xor     eax, eax
0x14008ebd7  mov     [rbp+4Fh+KeyHandle], 0
0x14008ebdf  mov     r12d, edx
0x14008ebe2  mov     [rbp+4Fh+Handle], 0
0x14008ebea  xor     esi, esi
0x14008ebec  mov     [r9], rax
0x14008ebef  xorps   xmm1, xmm1
0x14008ebf2  mov     [r15], rax
0x14008ebf5  mov     rdx, rcx; SourceString
0x14008ebf8  mov     [rbp+4Fh+P], rsi
0x14008ebfc  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x14008ec00  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14008ec04  mov     [rbp+4Fh+Length], esi
0x14008ec07  mov     r14, r9
0x14008ec0a  xor     edi, edi
0x14008ec0c  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x14008ec10  movups  [rbp+4Fh+var_70], xmm1
0x14008ec14  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x14008ec18  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x14008ec1c  call    cs:__imp_RtlInitUnicodeString
0x14008ec23  nop     dword ptr [rax+rax+00h]
0x14008ec28  lea     rax, [rbp+4Fh+DestinationString]
0x14008ec2c  mov     [rsp+0C0h+Disposition], rsi; Disposition
0x14008ec31  xorps   xmm0, xmm0
0x14008ec34  mov     [rsp+0C0h+CreateOptions], esi; CreateOptions
0x14008ec38  xor     r9d, r9d; TitleIndex
0x14008ec3b  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x14008ec3f  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14008ec43  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14008ec4a  mov     edx, 2001Fh; DesiredAccess
0x14008ec4f  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rsi
0x14008ec53  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x14008ec57  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x14008ec5e  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14008ec63  mov     [rsp+0C0h+Class], rsi; Class
0x14008ec68  call    cs:__imp_ZwCreateKey
0x14008ec6f  nop     dword ptr [rax+rax+00h]
0x14008ec74  mov     ebx, eax
0x14008ec76  test    eax, eax
0x14008ec78  js      loc_14008EDAD
0x14008ec7e  mov     [rbp+4Fh+Length], 98h
0x14008ec85  test    rdi, rdi
0x14008ec88  jnz     loc_14008EE07
0x14008ec8e  mov     edx, [rbp+4Fh+Length]
0x14008ec91  lea     r9, UxLowPriorityPool
0x14008ec98  mov     ecx, 102h
0x14008ec9d  mov     dword ptr [rsp+0C0h+Class], 1
0x14008eca5  mov     r8d, 44526C55h
0x14008ecab  call    cs:__imp_ExAllocatePool3
0x14008ecb2  nop     dword ptr [rax+rax+00h]
0x14008ecb7  mov     rdi, rax
0x14008ecba  test    rax, rax
0x14008ecbd  jz      loc_14008EE38
0x14008ecc3  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x14008ecc7  lea     rax, [rbp+4Fh+Length]
0x14008eccb  mov     qword ptr [rsp+0C0h+CreateOptions], rax; ResultLength
0x14008ecd0  mov     r9, rdi; KeyInformation
0x14008ecd3  mov     eax, [rbp+4Fh+Length]
0x14008ecd6  xor     r8d, r8d; KeyInformationClass
0x14008ecd9  mov     edx, r12d; Index
0x14008ecdc  mov     dword ptr [rsp+0C0h+Class], eax; Length
0x14008ece0  call    cs:__imp_ZwEnumerateKey
0x14008ece7  nop     dword ptr [rax+rax+00h]
0x14008ecec  mov     ebx, eax
0x14008ecee  cmp     eax, 80000005h
0x14008ecf3  jz      short loc_14008EC85
0x14008ecf5  cmp     eax, 0C0000023h
0x14008ecfa  jz      short loc_14008EC85
0x14008ecfc  test    eax, eax
0x14008ecfe  js      loc_14008EDAD
0x14008ed04  mov     eax, [rdi+0Ch]
0x14008ed07  test    al, 1
0x14008ed09  jnz     loc_14008EE00
0x14008ed0f  cmp     eax, 0FFFEh
0x14008ed14  ja      loc_14008EE00
0x14008ed1a  xorps   xmm0, xmm0
0x14008ed1d  lea     rsi, [rdi+10h]
0x14008ed21  mov     qword ptr [rbp+4Fh+var_70+8], rsi
0x14008ed25  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14008ed29  movzx   eax, word ptr [rdi+0Ch]
0x14008ed2d  lea     rcx, [rbp+4Fh+Handle]; KeyHandle
0x14008ed31  mov     word ptr [rbp+4Fh+var_70], ax
0x14008ed35  mov     edx, 20019h; DesiredAccess
0x14008ed3a  movzx   eax, word ptr [rdi+0Ch]
0x14008ed3e  mov     word ptr [rbp+4Fh+var_70+2], ax
0x14008ed42  mov     rax, [rbp+4Fh+KeyHandle]
0x14008ed46  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x14008ed4a  lea     rax, [rbp+4Fh+var_70]
0x14008ed4e  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x14008ed52  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14008ed59  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x14008ed60  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14008ed65  call    cs:__imp_ZwOpenKey
0x14008ed6c  nop     dword ptr [rax+rax+00h]
0x14008ed71  mov     ebx, eax
0x14008ed73  test    eax, eax
0x14008ed75  js      short loc_14008EDAD
0x14008ed77  mov     edx, [rdi+0Ch]
0x14008ed7a  lea     r8, [rbp+4Fh+P]
0x14008ed7e  shr     rdx, 1
0x14008ed81  mov     rcx, rsi; Src
0x14008ed84  call    UlAllocateWideString
0x14008ed89  mov     ebx, eax
0x14008ed8b  test    eax, eax
0x14008ed8d  jns     loc_14008EE1D
0x14008ed93  mov     rsi, [rbp+4Fh+P]
0x14008ed97  test    rsi, rsi
0x14008ed9a  jz      short loc_14008EDAD
0x14008ed9c  xor     edx, edx; Tag
0x14008ed9e  mov     rcx, rsi; P
0x14008eda1  call    cs:__imp_ExFreePoolWithTag
0x14008eda8  nop     dword ptr [rax+rax+00h]
0x14008edad  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x14008edb1  test    rcx, rcx
0x14008edb4  jz      short loc_14008EDC2
0x14008edb6  call    cs:__imp_ZwClose
0x14008edbd  nop     dword ptr [rax+rax+00h]
0x14008edc2  mov     rcx, [rbp+4Fh+Handle]; Handle
0x14008edc6  test    rcx, rcx
0x14008edc9  jnz     short loc_14008EE42
0x14008edcb  test    rdi, rdi
0x14008edce  jz      short loc_14008EDE1
0x14008edd0  xor     edx, edx; Tag
0x14008edd2  mov     rcx, rdi; P
0x14008edd5  call    cs:__imp_ExFreePoolWithTag
0x14008eddc  nop     dword ptr [rax+rax+00h]
0x14008ede1  lea     r11, [rsp+0C0h+var_20]
0x14008ede9  mov     eax, ebx
0x14008edeb  mov     rbx, [r11+30h]
0x14008edef  mov     rsi, [r11+38h]
0x14008edf3  mov     rsp, r11
0x14008edf6  pop     r15
0x14008edf8  pop     r14
0x14008edfa  pop     r12
0x14008edfc  pop     rdi
0x14008edfd  pop     rbp
0x14008edfe  retn
0x14008ee00  mov     ebx, 0C000014Ch
0x14008ee05  jmp     short loc_14008ED97
0x14008ee07  xor     edx, edx; Tag
0x14008ee09  mov     rcx, rdi; P
0x14008ee0c  call    cs:__imp_ExFreePoolWithTag
0x14008ee13  nop     dword ptr [rax+rax+00h]
0x14008ee18  jmp     loc_14008EC8E
0x14008ee1d  mov     rax, [rbp+4Fh+Handle]
0x14008ee21  mov     [r15], rax
0x14008ee24  mov     rax, [rbp+4Fh+P]
0x14008ee28  mov     [r14], rax
0x14008ee2b  mov     [rbp+4Fh+Handle], 0
0x14008ee33  jmp     loc_14008EDAD
0x14008ee38  mov     ebx, 0C000009Ah
0x14008ee3d  jmp     loc_14008EDAD
0x14008ee42  call    cs:__imp_ZwClose
0x14008ee49  nop     dword ptr [rax+rax+00h]
0x14008ee4e  jmp     loc_14008EDCB
```
