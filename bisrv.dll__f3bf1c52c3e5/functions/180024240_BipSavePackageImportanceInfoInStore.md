# BipSavePackageImportanceInfoInStore

- ea: `0x180024240`
- end: `0x180024552`
- name: `BipSavePackageImportanceInfoInStore`
- size: `786`
- prototype: `__int64 __fastcall(PCWSTR Source, PSID Sid)`
- caller_count: `3`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002e7a4`
- `0x180035f70`
- `0x18004b890`

## callees

- `0x180024240`
- `0x180024558`
- `0x180024b54`
- `0x180025630`
- `0x180025d68`
- `0x180025fcc`
- `0x180049844`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180024308`
- `ntdll!NtOpenKey` at `0x1800243b9`
- `ntdll!NtOpenKey` at `0x180024308`
- `ntdll!NtOpenKey` at `0x1800243b9`
- `ntdll!RtlInitUnicodeString` at `0x180024295`
- `ntdll!RtlInitUnicodeString` at `0x1800242a1`
- `ntdll!RtlInitUnicodeString` at `0x1800242ad`
- `ntdll!RtlInitUnicodeString` at `0x1800242cc`
- `ntdll!RtlInitUnicodeString` at `0x1800243ef`
- `ntdll!RtlInitUnicodeString` at `0x18002441a`
- `ntdll!RtlInitUnicodeString` at `0x180024445`
- `ntdll!RtlInitUnicodeString` at `0x180024472`
- `ntdll!RtlInitUnicodeString` at `0x18002449e`
- `ntdll!RtlInitUnicodeString` at `0x1800244cb`
- `ntdll!RtlInitUnicodeString` at `0x180024295`
- `ntdll!RtlInitUnicodeString` at `0x1800242a1`
- `ntdll!RtlInitUnicodeString` at `0x1800242ad`
- `ntdll!RtlInitUnicodeString` at `0x1800242cc`
- `ntdll!RtlInitUnicodeString` at `0x1800243ef`
- `ntdll!RtlInitUnicodeString` at `0x18002441a`
- `ntdll!RtlInitUnicodeString` at `0x180024445`
- `ntdll!RtlInitUnicodeString` at `0x180024472`
- `ntdll!RtlInitUnicodeString` at `0x18002449e`
- `ntdll!RtlInitUnicodeString` at `0x1800244cb`
- `ntdll!RtlFreeHeap` at `0x180024547`
- `ntdll!RtlFreeHeap` at `0x180024547`
- `ntdll!NtClose` at `0x180024345`
- `ntdll!NtClose` at `0x180024533`
- `ntdll!NtClose` at `0x180024345`
- `ntdll!NtClose` at `0x180024533`

## pseudocode

```c
__int64 __fastcall BipSavePackageImportanceInfoInStore(PCWSTR Source, PSID Sid, __int64 a3, __int64 a4)
{
  int v7; // ebx
  int v9; // eax
  HANDLE Handle; // [rsp+20h] [rbp-49h] BYREF
  void *KeyHandle; // [rsp+28h] [rbp-41h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING v14; // [rsp+50h] [rbp-19h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF

  Handle = 0;
  KeyHandle = 0;
  DestinationString = 0;
  v14 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&v14, 0);
  RtlInitUnicodeString(&ValueName, 0);
  if ( ::KeyHandle )
  {
    RtlInitUnicodeString(&v14, L"PackageImportance");
    ObjectAttributes.RootDirectory = ::KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &v14;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes) != -1073741772
      || (v7 = BipCreateKey(::KeyHandle, &KeyHandle, &v14), v7 >= 0) )
    {
      v9 = BipConstructPackageImportanceKeyName(Source, Sid, &DestinationString);
      v7 = v9;
      if ( v9 < 0 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            63,
            WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids,
            (unsigned int)v9);
      }
      else
      {
        ObjectAttributes.RootDirectory = ::KeyHandle;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( NtOpenKey(&Handle, 0xF003Fu, &ObjectAttributes) != -1073741772
          || (v7 = BipCreateKey(::KeyHandle, &Handle, &DestinationString), v7 >= 0) )
        {
          RtlInitUnicodeString(&ValueName, L"LastForegroundTime");
          v7 = BipWriteRegUlong64(Handle, &ValueName);
          if ( v7 >= 0 )
          {
            RtlInitUnicodeString(&ValueName, L"UsageHistoryStartTime");
            v7 = BipWriteRegUlong64(Handle, &ValueName);
            if ( v7 >= 0 )
            {
              RtlInitUnicodeString(&ValueName, L"UsageHistoryStartIndex");
              v7 = BipWriteRegUlong(Handle, &ValueName);
              if ( v7 >= 0 )
              {
                RtlInitUnicodeString(&ValueName, L"UsageHistoryIntervalLength");
                v7 = BipWriteRegUlong64(Handle, &ValueName);
                if ( v7 >= 0 )
                {
                  RtlInitUnicodeString(&ValueName, L"UsageHistoryLength");
                  v7 = BipWriteRegUlong(Handle, &ValueName);
                  if ( v7 >= 0 )
                  {
                    RtlInitUnicodeString(&ValueName, L"UsageHistory");
                    v7 = BipWriteRegBinary(
                           Handle,
                           &ValueName,
                           *(PVOID *)(a4 + 24),
                           2 * (unsigned int)*(unsigned __int8 *)(a4 + 17));
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v7 = -1073741816;
  }
  if ( Handle )
    NtClose(Handle);
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( DestinationString.Buffer )
    RtlFreeHeap(BipHeap, 0, DestinationString.Buffer);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180024240  push    rbp
0x180024242  push    rbx
0x180024243  push    rsi
0x180024244  push    rdi
0x180024245  push    r14
0x180024247  push    r15
0x180024249  lea     rbp, [rsp-2Fh]
0x18002424e  sub     rsp, 98h
0x180024255  xorps   xmm0, xmm0
0x180024258  mov     [rbp+57h+Handle], 0
0x180024260  mov     rsi, rdx
0x180024263  mov     [rbp+57h+KeyHandle], 0
0x18002426b  mov     r14, rcx
0x18002426e  xorps   xmm1, xmm1
0x180024271  xor     edx, edx; SourceString
0x180024273  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180024277  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002427b  mov     rdi, r9
0x18002427e  mov     r15, r8
0x180024281  movups  xmmword ptr [rbp+57h+var_70.Length], xmm1
0x180024285  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180024289  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002428d  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180024291  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x180024295  call    cs:__imp_RtlInitUnicodeString
0x18002429b  xor     edx, edx; SourceString
0x18002429d  lea     rcx, [rbp+57h+var_70]; DestinationString
0x1800242a1  call    cs:__imp_RtlInitUnicodeString
0x1800242a7  xor     edx, edx; SourceString
0x1800242a9  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800242ad  call    cs:__imp_RtlInitUnicodeString
0x1800242b3  cmp     cs:KeyHandle, 0
0x1800242bb  jz      loc_1800244F1
0x1800242c1  lea     rdx, SourceString; "PackageImportance"
0x1800242c8  lea     rcx, [rbp+57h+var_70]; DestinationString
0x1800242cc  call    cs:__imp_RtlInitUnicodeString
0x1800242d2  mov     rax, cs:KeyHandle
0x1800242d9  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800242dd  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800242e1  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800242e5  lea     rax, [rbp+57h+var_70]
0x1800242e9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800242f0  xorps   xmm0, xmm0
0x1800242f3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800242f7  mov     edx, 0F003Fh; DesiredAccess
0x1800242fc  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180024303  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180024308  call    cs:__imp_NtOpenKey
0x18002430e  cmp     eax, 0C0000034h
0x180024313  jnz     short loc_18002436A
0x180024315  mov     rcx, cs:KeyHandle
0x18002431c  lea     r8, [rbp+57h+var_70]
0x180024320  lea     rdx, [rbp+57h+KeyHandle]
0x180024324  call    BipCreateKey
0x180024329  mov     ebx, eax
0x18002432b  test    eax, eax
0x18002432d  jns     short loc_18002436A
0x18002432f  mov     rcx, [rbp+57h+Handle]; Handle
0x180024333  test    rcx, rcx
0x180024336  jnz     loc_180024533
0x18002433c  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180024340  test    rcx, rcx
0x180024343  jz      short loc_18002434B
0x180024345  call    cs:__imp_NtClose
0x18002434b  mov     r8, [rbp+57h+DestinationString.Buffer]; P
0x18002434f  test    r8, r8
0x180024352  jnz     loc_18002453E
0x180024358  mov     eax, ebx
0x18002435a  add     rsp, 98h
0x180024361  pop     r15
0x180024363  pop     r14
0x180024365  pop     rdi
0x180024366  pop     rsi
0x180024367  pop     rbx
0x180024368  pop     rbp
0x180024369  retn
0x18002436a  lea     r8, [rbp+57h+DestinationString]; Destination
0x18002436e  mov     rdx, rsi; Sid
0x180024371  mov     rcx, r14; Source
0x180024374  call    ?BipConstructPackageImportanceKeyName@@YAJPEBGPEAXPEAU_UNICODE_STRING@@@Z; BipConstructPackageImportanceKeyName(ushort const *,void *,_UNICODE_STRING *)
0x180024379  mov     ebx, eax
0x18002437b  test    eax, eax
0x18002437d  js      loc_1800244FB
0x180024383  mov     rax, cs:KeyHandle
0x18002438a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002438e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180024392  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x180024396  lea     rax, [rbp+57h+DestinationString]
0x18002439a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800243a1  xorps   xmm0, xmm0
0x1800243a4  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800243a8  mov     edx, 0F003Fh; DesiredAccess
0x1800243ad  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800243b4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800243b9  call    cs:__imp_NtOpenKey
0x1800243bf  cmp     eax, 0C0000034h
0x1800243c4  jnz     short loc_1800243E4
0x1800243c6  mov     rcx, cs:KeyHandle
0x1800243cd  lea     r8, [rbp+57h+DestinationString]
0x1800243d1  lea     rdx, [rbp+57h+Handle]
0x1800243d5  call    BipCreateKey
0x1800243da  mov     ebx, eax
0x1800243dc  test    eax, eax
0x1800243de  js      loc_18002432F
0x1800243e4  lea     rdx, aLastforeground; "LastForegroundTime"
0x1800243eb  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800243ef  call    cs:__imp_RtlInitUnicodeString
0x1800243f5  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1800243f9  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800243fd  mov     r8, r15
0x180024400  call    BipWriteRegUlong64
0x180024405  mov     ebx, eax
0x180024407  test    eax, eax
0x180024409  js      loc_18002432F
0x18002440f  lea     rdx, aUsagehistoryst_0; "UsageHistoryStartTime"
0x180024416  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x18002441a  call    cs:__imp_RtlInitUnicodeString
0x180024420  mov     r8, [rdi]
0x180024423  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180024427  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x18002442b  call    BipWriteRegUlong64
0x180024430  mov     ebx, eax
0x180024432  test    eax, eax
0x180024434  js      loc_18002432F
0x18002443a  lea     rdx, aUsagehistoryst; "UsageHistoryStartIndex"
0x180024441  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180024445  call    cs:__imp_RtlInitUnicodeString
0x18002444b  movzx   r8d, byte ptr [rdi+10h]
0x180024450  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180024454  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x180024458  call    BipWriteRegUlong
0x18002445d  mov     ebx, eax
0x18002445f  test    eax, eax
0x180024461  js      loc_18002432F
0x180024467  lea     rdx, aUsagehistoryin; "UsageHistoryIntervalLength"
0x18002446e  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180024472  call    cs:__imp_RtlInitUnicodeString
0x180024478  mov     r8, [rdi+8]
0x18002447c  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180024480  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x180024484  call    BipWriteRegUlong64
0x180024489  mov     ebx, eax
0x18002448b  test    eax, eax
0x18002448d  js      loc_18002432F
0x180024493  lea     rdx, aUsagehistoryle; "UsageHistoryLength"
0x18002449a  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x18002449e  call    cs:__imp_RtlInitUnicodeString
0x1800244a4  movzx   r8d, byte ptr [rdi+11h]
0x1800244a9  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800244ad  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1800244b1  call    BipWriteRegUlong
0x1800244b6  mov     ebx, eax
0x1800244b8  test    eax, eax
0x1800244ba  js      loc_18002432F
0x1800244c0  lea     rdx, aUsagehistory; "UsageHistory"
0x1800244c7  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800244cb  call    cs:__imp_RtlInitUnicodeString
0x1800244d1  movzx   r9d, byte ptr [rdi+11h]
0x1800244d6  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800244da  mov     r8, [rdi+18h]; Data
0x1800244de  add     r9d, r9d; DataSize
0x1800244e1  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1800244e5  call    BipWriteRegBinary
0x1800244ea  mov     ebx, eax
0x1800244ec  jmp     loc_18002432F
0x1800244f1  mov     ebx, 0C0000008h
0x1800244f6  jmp     loc_18002432F
0x1800244fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180024502  test    byte ptr [rcx+1Ch], 8
0x180024506  jz      loc_18002432F
0x18002450c  cmp     byte ptr [rcx+19h], 2
0x180024510  jb      loc_18002432F
0x180024516  mov     rcx, [rcx+10h]
0x18002451a  lea     r8, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids
0x180024521  mov     edx, 3Fh ; '?'
0x180024526  mov     r9d, eax
0x180024529  call    WPP_SF_d
0x18002452e  jmp     loc_18002432F
0x180024533  call    cs:__imp_NtClose
0x180024539  jmp     loc_18002433C
0x18002453e  mov     rcx, cs:BipHeap; HeapHandle
0x180024545  xor     edx, edx; Flags
0x180024547  call    cs:__imp_RtlFreeHeap
0x18002454d  jmp     loc_180024358
```
