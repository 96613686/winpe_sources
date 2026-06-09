# BaseSrvRefreshIniFileMapping

- ea: `0x180005f10`
- end: `0x1800061da`
- name: `BaseSrvRefreshIniFileMapping`
- size: `714`
- prototype: `NTSTATUS __fastcall(UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005210`
- `0x180005bc0`
- `0x180005f10`
- `0x18000c9c4`
- `0x18000caf0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180006018`
- `ntdll!NtOpenKey` at `0x180006065`
- `ntdll!NtOpenKey` at `0x180006018`
- `ntdll!NtOpenKey` at `0x180006065`
- `ntdll!NtClose` at `0x18000607f`
- `ntdll!NtClose` at `0x1800061c9`
- `ntdll!NtClose` at `0x18000607f`
- `ntdll!NtClose` at `0x1800061c9`
- `ntdll!RtlEqualUnicodeString` at `0x180006116`
- `ntdll!RtlEqualUnicodeString` at `0x18000619c`
- `ntdll!RtlEqualUnicodeString` at `0x180006116`
- `ntdll!RtlEqualUnicodeString` at `0x18000619c`
- `ntdll!RtlLockHeap` at `0x1800060f0`
- `ntdll!RtlLockHeap` at `0x1800060f0`
- `ntdll!RtlUnlockHeap` at `0x18000617b`
- `ntdll!RtlUnlockHeap` at `0x18000617b`
- `ntdll!RtlInitUnicodeString` at `0x180005fa7`
- `ntdll!RtlInitUnicodeString` at `0x180005fba`
- `ntdll!RtlInitUnicodeString` at `0x180005fd2`
- `ntdll!RtlInitUnicodeString` at `0x180005fa7`
- `ntdll!RtlInitUnicodeString` at `0x180005fba`
- `ntdll!RtlInitUnicodeString` at `0x180005fd2`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180005f87`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180005f87`

## string_xrefs

- `0x180005fc6`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\IniFileMapping`

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
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
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
0x180005f10  mov     rax, rsp
0x180005f13  mov     [rax+10h], rbx
0x180005f17  push    rsi
0x180005f18  push    rdi
0x180005f19  push    r12
0x180005f1b  push    r14
0x180005f1d  push    r15
0x180005f1f  sub     rsp, 80h
0x180005f26  mov     r10, rcx
0x180005f29  lea     rbx, [rcx+40h]
0x180005f2d  xor     r12d, r12d
0x180005f30  mov     [rax+20h], r12
0x180005f34  mov     [rax+8], r12
0x180005f38  xorps   xmm0, xmm0
0x180005f3b  movups  xmmword ptr [rsp+0A8h+var_88.Length], xmm0
0x180005f40  mov     [rax-54h], r12d
0x180005f44  mov     [rax-3Ch], r12d
0x180005f48  mov     [rax+18h], r12
0x180005f4c  movups  xmmword ptr [rax-78h], xmm0
0x180005f50  xorps   xmm1, xmm1
0x180005f53  movups  xmmword ptr [rax-68h], xmm1
0x180005f57  movzx   ecx, word ptr [rbx]
0x180005f5a  test    cl, 1
0x180005f5d  jnz     loc_1800060A6
0x180005f63  movzx   eax, word ptr [rbx+2]
0x180005f67  test    al, 1
0x180005f69  jnz     loc_1800060A6
0x180005f6f  cmp     cx, ax
0x180005f72  ja      loc_1800060A6
0x180005f78  mov     r8d, eax
0x180005f7b  lea     rdx, [rbx+8]
0x180005f7f  lea     r9d, [r12+1]
0x180005f84  mov     rcx, r10
0x180005f87  call    cs:__imp_CsrValidateMessageBuffer
0x180005f8e  nop     dword ptr [rax+rax+00h]
0x180005f93  test    al, al
0x180005f95  jz      loc_1800060A6
0x180005f9b  lea     rdx, aWinIni; "win.ini"
0x180005fa2  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x180005fa7  call    cs:__imp_RtlInitUnicodeString
0x180005fae  nop     dword ptr [rax+rax+00h]
0x180005fb3  xor     edx, edx; SourceString
0x180005fb5  lea     rcx, [rsp+0A8h+var_68]; DestinationString
0x180005fba  call    cs:__imp_RtlInitUnicodeString
0x180005fc1  nop     dword ptr [rax+rax+00h]
0x180005fc6  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x180005fcd  lea     rcx, [rsp+0A8h+var_88]; DestinationString
0x180005fd2  call    cs:__imp_RtlInitUnicodeString
0x180005fd9  nop     dword ptr [rax+rax+00h]
0x180005fde  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x180005fe6  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x180005feb  mov     [rsp+0A8h+ObjectAttributes.Attributes], 40h ; '@'
0x180005ff3  lea     rax, [rsp+0A8h+var_88]
0x180005ff8  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x180005ffd  xorps   xmm0, xmm0
0x180006000  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006006  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x18000600b  mov     edx, 80000000h; DesiredAccess
0x180006010  lea     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x180006018  call    cs:__imp_NtOpenKey
0x18000601f  nop     dword ptr [rax+rax+00h]
0x180006024  test    eax, eax
0x180006026  js      short loc_18000608D
0x180006028  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x180006030  mov     rax, [rsp+0A8h+KeyHandle]
0x180006038  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], rax
0x18000603d  mov     [rsp+0A8h+ObjectAttributes.Attributes], 40h ; '@'
0x180006045  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rbx
0x18000604a  xorps   xmm0, xmm0
0x18000604d  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006053  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x180006058  mov     edx, 80000000h; DesiredAccess
0x18000605d  lea     rcx, [rsp+0A8h+Handle]; KeyHandle
0x180006065  call    cs:__imp_NtOpenKey
0x18000606c  nop     dword ptr [rax+rax+00h]
0x180006071  mov     edi, eax
0x180006073  test    eax, eax
0x180006075  jns     short loc_1800060AD
0x180006077  mov     rcx, [rsp+0A8h+KeyHandle]; Handle
0x18000607f  call    cs:__imp_NtClose
0x180006086  nop     dword ptr [rax+rax+00h]
0x18000608b  mov     eax, edi
0x18000608d  mov     rbx, [rsp+0A8h+arg_8]
0x180006095  add     rsp, 80h
0x18000609c  pop     r15
0x18000609e  pop     r14
0x1800060a0  pop     r12
0x1800060a2  pop     rdi
0x1800060a3  pop     rsi
0x1800060a4  retn
0x1800060a6  mov     eax, 0C000000Dh
0x1800060ab  jmp     short loc_18000608D
0x1800060ad  lea     rdx, [rsp+0A8h+P]
0x1800060b5  mov     rcx, rbx; SourceString
0x1800060b8  call    BaseSrvSaveFileNameMapping
0x1800060bd  mov     edi, eax
0x1800060bf  test    eax, eax
0x1800060c1  js      loc_1800061C1
0x1800060c7  mov     rdx, [rsp+0A8h+Handle]
0x1800060cf  mov     rsi, [rsp+0A8h+P]
0x1800060d7  mov     rcx, rsi
0x1800060da  call    BaseSrvSaveIniFileMapping
0x1800060df  mov     edi, eax
0x1800060e1  test    eax, eax
0x1800060e3  js      loc_1800061B9
0x1800060e9  mov     rcx, cs:BaseSrvSharedHeap; Heap
0x1800060f0  call    cs:__imp_RtlLockHeap
0x1800060f7  nop     dword ptr [rax+rax+00h]
0x1800060fc  nop
0x1800060fd  mov     r15, cs:BaseSrvIniFileMapping
0x180006104  mov     r14, [r15]
0x180006107  test    r14, r14
0x18000610a  jz      short loc_180006153
0x18000610c  lea     rcx, [r14+8]; String1
0x180006110  mov     r8b, 1; CaseInsensitive
0x180006113  mov     rdx, rbx; String2
0x180006116  call    cs:__imp_RtlEqualUnicodeString
0x18000611d  nop     dword ptr [rax+rax+00h]
0x180006122  test    al, al
0x180006124  jz      short loc_180006163
0x180006126  mov     rdx, r14
0x180006129  mov     rcx, rsi
0x18000612c  call    BaseSrvEqualFileMappings
0x180006131  test    al, al
0x180006133  jz      short loc_18000614A
0x180006135  mov     rcx, rsi; P
0x180006138  call    BaseSrvFreeFileMapping
0x18000613d  mov     rsi, r12
0x180006140  mov     [rsp+0A8h+P], r12
0x180006148  jmp     short loc_180006168
0x18000614a  mov     rax, [r14]
0x18000614d  mov     [r15], rax
0x180006150  mov     [r14], r12
0x180006153  test    rsi, rsi
0x180006156  jz      short loc_180006168
0x180006158  mov     rax, [r15]
0x18000615b  mov     [rsi], rax
0x18000615e  mov     [r15], rsi
0x180006161  jmp     short loc_180006168
0x180006163  mov     r15, r14
0x180006166  jmp     short loc_180006104
0x180006168  jmp     short loc_180006174
0x18000616a  mov     edi, eax
0x18000616c  mov     rsi, [rsp+0A8h+P]
0x180006174  mov     rcx, cs:BaseSrvSharedHeap; Heap
0x18000617b  call    cs:__imp_RtlUnlockHeap
0x180006182  nop     dword ptr [rax+rax+00h]
0x180006187  test    edi, edi
0x180006189  js      short loc_1800061C1
0x18000618b  test    rsi, rsi
0x18000618e  jz      short loc_1800061C1
0x180006190  lea     rcx, [rsi+8]; String1
0x180006194  mov     r8b, 1; CaseInsensitive
0x180006197  lea     rdx, [rsp+0A8h+DestinationString]; String2
0x18000619c  call    cs:__imp_RtlEqualUnicodeString
0x1800061a3  nop     dword ptr [rax+rax+00h]
0x1800061a8  test    al, al
0x1800061aa  jz      short loc_1800061C1
0x1800061ac  mov     rax, cs:BaseSrvIniFileMapping
0x1800061b3  mov     [rax+10h], rsi
0x1800061b7  jmp     short loc_1800061C1
0x1800061b9  mov     rcx, rsi; P
0x1800061bc  call    BaseSrvFreeFileMapping
0x1800061c1  mov     rcx, [rsp+0A8h+Handle]; Handle
0x1800061c9  call    cs:__imp_NtClose
0x1800061d0  nop     dword ptr [rax+rax+00h]
0x1800061d5  jmp     loc_180006077
```
