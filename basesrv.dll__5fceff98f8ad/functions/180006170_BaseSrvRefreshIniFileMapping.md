# BaseSrvRefreshIniFileMapping

- ea: `0x180006170`
- end: `0x180006446`
- name: `BaseSrvRefreshIniFileMapping`
- size: `726`
- prototype: `NTSTATUS __fastcall(UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005200`
- `0x180005b60`
- `0x180006170`
- `0x18000cda8`
- `0x18000ced4`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180006284`
- `ntdll!NtOpenKey` at `0x1800062d1`
- `ntdll!NtOpenKey` at `0x180006284`
- `ntdll!NtOpenKey` at `0x1800062d1`
- `ntdll!NtClose` at `0x1800062eb`
- `ntdll!NtClose` at `0x180006435`
- `ntdll!NtClose` at `0x1800062eb`
- `ntdll!NtClose` at `0x180006435`
- `ntdll!RtlEqualUnicodeString` at `0x180006382`
- `ntdll!RtlEqualUnicodeString` at `0x180006408`
- `ntdll!RtlEqualUnicodeString` at `0x180006382`
- `ntdll!RtlEqualUnicodeString` at `0x180006408`
- `ntdll!RtlLockHeap` at `0x18000635c`
- `ntdll!RtlLockHeap` at `0x18000635c`
- `ntdll!RtlUnlockHeap` at `0x1800063e7`
- `ntdll!RtlUnlockHeap` at `0x1800063e7`
- `ntdll!RtlInitUnicodeString` at `0x180006213`
- `ntdll!RtlInitUnicodeString` at `0x180006226`
- `ntdll!RtlInitUnicodeString` at `0x18000623e`
- `ntdll!RtlInitUnicodeString` at `0x180006213`
- `ntdll!RtlInitUnicodeString` at `0x180006226`
- `ntdll!RtlInitUnicodeString` at `0x18000623e`
- `CSRSRV!CsrValidateMessageBuffer` at `0x1800061f3`
- `CSRSRV!CsrValidateMessageBuffer` at `0x1800061f3`

## string_xrefs

- `0x180006232`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\IniFileMapping`

## pseudocode

```c
NTSTATUS __fastcall BaseSrvRefreshIniFileMapping(UNICODE_STRING *a1)
{
  UNICODE_STRING *v2; // rbx
  USHORT Length; // cx
  USHORT MaximumLength; // ax
  NTSTATUS result; // eax
  NTSTATUS v6; // edi
  __int64 *i; // r15
  __int64 v8; // r14
  struct _UNICODE_STRING v9; // [rsp+20h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-78h] BYREF
  struct _UNICODE_STRING v11; // [rsp+40h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-58h] BYREF
  HANDLE Handle; // [rsp+C0h] [rbp+18h] BYREF
  void *KeyHandle; // [rsp+C8h] [rbp+20h] BYREF

  v2 = a1 + 4;
  KeyHandle = 0;
  v9 = 0;
  memset(&ObjectAttributes, 0, 44);
  Handle = 0;
  DestinationString = 0;
  v11 = 0;
  Length = a1[4].Length;
  if ( (Length & 1) != 0 )
    return -1073741811;
  MaximumLength = v2->MaximumLength;
  if ( (MaximumLength & 1) != 0
    || Length > MaximumLength
    || !(unsigned __int8)CsrValidateMessageBuffer(a1, &v2->Buffer, v2->MaximumLength, 1) )
  {
    return -1073741811;
  }
  RtlInitUnicodeString(&DestinationString, L"win.ini");
  RtlInitUnicodeString(&v11, 0);
  RtlInitUnicodeString(&v9, L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\IniFileMapping");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &v9;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
  if ( result >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = v2;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = NtOpenKey(&Handle, 0x80000000, &ObjectAttributes);
    if ( v6 >= 0 )
    {
      v6 = BaseSrvSaveFileNameMapping(v2);
      if ( v6 >= 0 )
      {
        v6 = BaseSrvSaveIniFileMapping(0, Handle);
        if ( v6 < 0 )
        {
          BaseSrvFreeFileMapping(0);
        }
        else
        {
          RtlLockHeap(BaseSrvSharedHeap);
          for ( i = (__int64 *)BaseSrvIniFileMapping; ; i = (__int64 *)v8 )
          {
            v8 = *i;
            if ( !*i )
              break;
            if ( RtlEqualUnicodeString((PCUNICODE_STRING)(v8 + 8), v2, 1u) )
            {
              if ( (unsigned __int8)BaseSrvEqualFileMappings(0, v8) )
              {
                BaseSrvFreeFileMapping(0);
              }
              else
              {
                *i = *(_QWORD *)v8;
                *(_QWORD *)v8 = 0;
              }
              break;
            }
          }
          RtlUnlockHeap(BaseSrvSharedHeap);
        }
      }
      NtClose(Handle);
    }
    NtClose(KeyHandle);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180006170  mov     r11, rsp
0x180006173  mov     [r11+10h], rbx
0x180006177  push    rsi
0x180006178  push    rdi
0x180006179  push    r12
0x18000617b  push    r14
0x18000617d  push    r15
0x18000617f  sub     rsp, 80h
0x180006186  mov     r10, rcx
0x180006189  lea     rbx, [rcx+40h]
0x18000618d  xor     r12d, r12d
0x180006190  mov     [r11+20h], r12
0x180006194  mov     [r11+8], r12
0x180006198  xorps   xmm0, xmm0
0x18000619b  movups  xmmword ptr [rsp+0A8h+var_88.Length], xmm0
0x1800061a0  xor     eax, eax
0x1800061a2  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x1800061a7  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x1800061ac  movups  xmmword ptr [rsp+0A8h+ObjectAttributes+1Ch], xmm0
0x1800061b1  mov     [r11+18h], r12
0x1800061b5  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm0
0x1800061ba  xorps   xmm1, xmm1
0x1800061bd  movups  xmmword ptr [rsp+0A8h+var_68.Length], xmm1
0x1800061c2  movzx   ecx, word ptr [rbx]
0x1800061c5  test    cl, 1
0x1800061c8  jnz     loc_180006312
0x1800061ce  movzx   eax, word ptr [rbx+2]
0x1800061d2  test    al, 1
0x1800061d4  jnz     loc_180006312
0x1800061da  cmp     cx, ax
0x1800061dd  ja      loc_180006312
0x1800061e3  mov     r8d, eax
0x1800061e6  lea     rdx, [rbx+8]
0x1800061ea  mov     r9d, 1
0x1800061f0  mov     rcx, r10
0x1800061f3  call    cs:__imp_CsrValidateMessageBuffer
0x1800061fa  nop     dword ptr [rax+rax+00h]
0x1800061ff  test    al, al
0x180006201  jz      loc_180006312
0x180006207  lea     rdx, aWinIni; "win.ini"
0x18000620e  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x180006213  call    cs:__imp_RtlInitUnicodeString
0x18000621a  nop     dword ptr [rax+rax+00h]
0x18000621f  xor     edx, edx; SourceString
0x180006221  lea     rcx, [rsp+0A8h+var_68]; DestinationString
0x180006226  call    cs:__imp_RtlInitUnicodeString
0x18000622d  nop     dword ptr [rax+rax+00h]
0x180006232  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x180006239  lea     rcx, [rsp+0A8h+var_88]; DestinationString
0x18000623e  call    cs:__imp_RtlInitUnicodeString
0x180006245  nop     dword ptr [rax+rax+00h]
0x18000624a  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x180006252  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x180006257  mov     [rsp+0A8h+ObjectAttributes.Attributes], 40h ; '@'
0x18000625f  lea     rax, [rsp+0A8h+var_88]
0x180006264  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x180006269  xorps   xmm0, xmm0
0x18000626c  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006272  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x180006277  mov     edx, 80000000h; DesiredAccess
0x18000627c  lea     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x180006284  call    cs:__imp_NtOpenKey
0x18000628b  nop     dword ptr [rax+rax+00h]
0x180006290  test    eax, eax
0x180006292  js      short loc_1800062F9
0x180006294  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x18000629c  mov     rax, [rsp+0A8h+KeyHandle]
0x1800062a4  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], rax
0x1800062a9  mov     [rsp+0A8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800062b1  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rbx
0x1800062b6  xorps   xmm0, xmm0
0x1800062b9  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800062bf  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x1800062c4  mov     edx, 80000000h; DesiredAccess
0x1800062c9  lea     rcx, [rsp+0A8h+Handle]; KeyHandle
0x1800062d1  call    cs:__imp_NtOpenKey
0x1800062d8  nop     dword ptr [rax+rax+00h]
0x1800062dd  mov     edi, eax
0x1800062df  test    eax, eax
0x1800062e1  jns     short loc_180006319
0x1800062e3  mov     rcx, [rsp+0A8h+KeyHandle]; Handle
0x1800062eb  call    cs:__imp_NtClose
0x1800062f2  nop     dword ptr [rax+rax+00h]
0x1800062f7  mov     eax, edi
0x1800062f9  mov     rbx, [rsp+0A8h+arg_8]
0x180006301  add     rsp, 80h
0x180006308  pop     r15
0x18000630a  pop     r14
0x18000630c  pop     r12
0x18000630e  pop     rdi
0x18000630f  pop     rsi
0x180006310  retn
0x180006312  mov     eax, 0C000000Dh
0x180006317  jmp     short loc_1800062F9
0x180006319  lea     rdx, [rsp+0A8h+P]
0x180006321  mov     rcx, rbx; SourceString
0x180006324  call    BaseSrvSaveFileNameMapping
0x180006329  mov     edi, eax
0x18000632b  test    eax, eax
0x18000632d  js      loc_18000642D
0x180006333  mov     rdx, [rsp+0A8h+Handle]
0x18000633b  mov     rsi, [rsp+0A8h+P]
0x180006343  mov     rcx, rsi
0x180006346  call    BaseSrvSaveIniFileMapping
0x18000634b  mov     edi, eax
0x18000634d  test    eax, eax
0x18000634f  js      loc_180006425
0x180006355  mov     rcx, cs:BaseSrvSharedHeap; Heap
0x18000635c  call    cs:__imp_RtlLockHeap
0x180006363  nop     dword ptr [rax+rax+00h]
0x180006368  nop
0x180006369  mov     r15, cs:BaseSrvIniFileMapping
0x180006370  mov     r14, [r15]
0x180006373  test    r14, r14
0x180006376  jz      short loc_1800063BF
0x180006378  lea     rcx, [r14+8]; String1
0x18000637c  mov     r8b, 1; CaseInsensitive
0x18000637f  mov     rdx, rbx; String2
0x180006382  call    cs:__imp_RtlEqualUnicodeString
0x180006389  nop     dword ptr [rax+rax+00h]
0x18000638e  test    al, al
0x180006390  jz      short loc_1800063CF
0x180006392  mov     rdx, r14
0x180006395  mov     rcx, rsi
0x180006398  call    BaseSrvEqualFileMappings
0x18000639d  test    al, al
0x18000639f  jz      short loc_1800063B6
0x1800063a1  mov     rcx, rsi; P
0x1800063a4  call    BaseSrvFreeFileMapping
0x1800063a9  mov     rsi, r12
0x1800063ac  mov     [rsp+0A8h+P], r12
0x1800063b4  jmp     short loc_1800063D4
0x1800063b6  mov     rax, [r14]
0x1800063b9  mov     [r15], rax
0x1800063bc  mov     [r14], r12
0x1800063bf  test    rsi, rsi
0x1800063c2  jz      short loc_1800063D4
0x1800063c4  mov     rax, [r15]
0x1800063c7  mov     [rsi], rax
0x1800063ca  mov     [r15], rsi
0x1800063cd  jmp     short loc_1800063D4
0x1800063cf  mov     r15, r14
0x1800063d2  jmp     short loc_180006370
0x1800063d4  jmp     short loc_1800063E0
0x1800063d6  mov     edi, eax
0x1800063d8  mov     rsi, [rsp+0A8h+P]
0x1800063e0  mov     rcx, cs:BaseSrvSharedHeap; Heap
0x1800063e7  call    cs:__imp_RtlUnlockHeap
0x1800063ee  nop     dword ptr [rax+rax+00h]
0x1800063f3  test    edi, edi
0x1800063f5  js      short loc_18000642D
0x1800063f7  test    rsi, rsi
0x1800063fa  jz      short loc_18000642D
0x1800063fc  lea     rcx, [rsi+8]; String1
0x180006400  mov     r8b, 1; CaseInsensitive
0x180006403  lea     rdx, [rsp+0A8h+DestinationString]; String2
0x180006408  call    cs:__imp_RtlEqualUnicodeString
0x18000640f  nop     dword ptr [rax+rax+00h]
0x180006414  test    al, al
0x180006416  jz      short loc_18000642D
0x180006418  mov     rax, cs:BaseSrvIniFileMapping
0x18000641f  mov     [rax+10h], rsi
0x180006423  jmp     short loc_18000642D
0x180006425  mov     rcx, rsi; P
0x180006428  call    BaseSrvFreeFileMapping
0x18000642d  mov     rcx, [rsp+0A8h+Handle]; Handle
0x180006435  call    cs:__imp_NtClose
0x18000643c  nop     dword ptr [rax+rax+00h]
0x180006441  jmp     loc_1800062E3
```
