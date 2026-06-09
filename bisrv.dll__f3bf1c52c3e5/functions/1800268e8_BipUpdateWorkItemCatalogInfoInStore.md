# BipUpdateWorkItemCatalogInfoInStore

- ea: `0x1800268e8`
- end: `0x180026b20`
- name: `BipUpdateWorkItemCatalogInfoInStore`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180063178`

## callees

- `0x180013d20`
- `0x180025f14`
- `0x180025fcc`
- `0x1800268e8`
- `0x180026b28`
- `0x180049844`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18002696b`
- `ntdll!NtOpenKey` at `0x18002696b`
- `ntdll!RtlInitUnicodeString` at `0x1800269e4`
- `ntdll!RtlInitUnicodeString` at `0x1800269f5`
- `ntdll!RtlInitUnicodeString` at `0x180026a21`
- `ntdll!RtlInitUnicodeString` at `0x180026a54`
- `ntdll!RtlInitUnicodeString` at `0x1800269e4`
- `ntdll!RtlInitUnicodeString` at `0x1800269f5`
- `ntdll!RtlInitUnicodeString` at `0x180026a21`
- `ntdll!RtlInitUnicodeString` at `0x180026a54`
- `ntdll!RtlFreeHeap` at `0x180026abd`
- `ntdll!RtlFreeHeap` at `0x180026abd`
- `ntdll!NtClose` at `0x1800269bb`
- `ntdll!NtClose` at `0x1800269bb`

## pseudocode

```c
__int64 __fastcall BipUpdateWorkItemCatalogInfoInStore(__int64 a1)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  struct _UNICODE_STRING ValueName; // [rsp+20h] [rbp-60h] BYREF
  PVOID P[2]; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+98h] [rbp+18h] BYREF

  KeyHandle = 0;
  *(_OWORD *)P = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  v2 = BipConstructWorkItemKeyName(a1, P);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 82;
      goto LABEL_18;
    }
  }
  else
  {
    ObjectAttributes.RootDirectory = ::KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v2 = NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
    v3 = v2;
    if ( v2 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, (PCWSTR)(*(_QWORD *)(a1 + 88) + 60LL));
      RtlInitUnicodeString(&ValueName, L"PackageRelativeAppName");
      v2 = BipWriteRegUnicodeString(KeyHandle, &ValueName);
      v3 = v2;
      if ( v2 < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v5 = 84;
          goto LABEL_18;
        }
      }
      else
      {
        RtlInitUnicodeString(&ValueName, L"PsmActivationType");
        BipGetActivationType(a1);
        v2 = BipWriteRegUlong(KeyHandle, &ValueName);
        v3 = v2;
        if ( v2 < 0 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v5 = 85;
            goto LABEL_18;
          }
        }
        else
        {
          RtlInitUnicodeString(&ValueName, L"PackageFlags");
          v2 = BipWriteRegUlong(KeyHandle, &ValueName);
          v3 = v2;
          if ( v2 < 0 )
          {
            v4 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v5 = 86;
              goto LABEL_18;
            }
          }
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 83;
LABEL_18:
        WPP_SF_d(v4[2], v5, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids, (unsigned int)v2);
      }
    }
  }
  if ( P[1] )
    RtlFreeHeap(BipHeap, 0, P[1]);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return v3;
}

```

## disassembly

```asm
0x1800268e8  mov     [rsp-8+arg_0], rbx
0x1800268ed  mov     [rsp-8+arg_10], rdi
0x1800268f2  push    rbp
0x1800268f3  mov     rbp, rsp
0x1800268f6  sub     rsp, 80h
0x1800268fd  xorps   xmm1, xmm1
0x180026900  mov     [rbp+KeyHandle], 0
0x180026908  xorps   xmm0, xmm0
0x18002690b  lea     rdx, [rbp+P]
0x18002690f  movups  xmmword ptr [rbp+P], xmm0
0x180026913  mov     rdi, rcx
0x180026916  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x18002691a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x18002691e  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x180026922  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180026926  movups  xmmword ptr [rbp+ValueName.Length], xmm1
0x18002692a  call    BipConstructWorkItemKeyName
0x18002692f  mov     ebx, eax
0x180026931  test    eax, eax
0x180026933  js      short loc_180026994
0x180026935  mov     rax, cs:KeyHandle
0x18002693c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180026940  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180026944  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180026948  lea     rax, [rbp+P]
0x18002694c  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180026953  xorps   xmm0, xmm0
0x180026956  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002695a  mov     edx, 0F003Fh; DesiredAccess
0x18002695f  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180026966  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002696b  call    cs:__imp_NtOpenKey
0x180026971  mov     ebx, eax
0x180026973  test    eax, eax
0x180026975  jns     short loc_1800269D8
0x180026977  mov     rcx, cs:WPP_GLOBAL_Control
0x18002697e  test    byte ptr [rcx+1Ch], 8
0x180026982  jz      short loc_1800269A5
0x180026984  cmp     byte ptr [rcx+19h], 2
0x180026988  jb      short loc_1800269A5
0x18002698a  mov     edx, 53h ; 'S'
0x18002698f  jmp     loc_180026A9C
0x180026994  mov     rcx, cs:WPP_GLOBAL_Control
0x18002699b  test    byte ptr [rcx+1Ch], 8
0x18002699f  jnz     loc_180026AC8
0x1800269a5  mov     r8, [rbp+P+8]; P
0x1800269a9  test    r8, r8
0x1800269ac  jnz     loc_180026AB4
0x1800269b2  mov     rcx, [rbp+KeyHandle]; Handle
0x1800269b6  test    rcx, rcx
0x1800269b9  jz      short loc_1800269C1
0x1800269bb  call    cs:__imp_NtClose
0x1800269c1  lea     r11, [rsp+80h+var_s0]
0x1800269c9  mov     eax, ebx
0x1800269cb  mov     rbx, [r11+10h]
0x1800269cf  mov     rdi, [r11+20h]
0x1800269d3  mov     rsp, r11
0x1800269d6  pop     rbp
0x1800269d7  retn
0x1800269d8  mov     rdx, [rdi+58h]
0x1800269dc  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800269e0  add     rdx, 3Ch ; '<'; SourceString
0x1800269e4  call    cs:__imp_RtlInitUnicodeString
0x1800269ea  lea     rdx, aPackagerelativ_0; "PackageRelativeAppName"
0x1800269f1  lea     rcx, [rbp+ValueName]; DestinationString
0x1800269f5  call    cs:__imp_RtlInitUnicodeString
0x1800269fb  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800269ff  lea     r8, [rbp+DestinationString]
0x180026a03  lea     rdx, [rbp+ValueName]; ValueName
0x180026a07  call    BipWriteRegUnicodeString
0x180026a0c  mov     ebx, eax
0x180026a0e  test    eax, eax
0x180026a10  js      loc_180026AD9
0x180026a16  lea     rdx, aPsmactivationt; "PsmActivationType"
0x180026a1d  lea     rcx, [rbp+ValueName]; DestinationString
0x180026a21  call    cs:__imp_RtlInitUnicodeString
0x180026a27  mov     rcx, rdi
0x180026a2a  call    BipGetActivationType
0x180026a2f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180026a33  lea     rdx, [rbp+ValueName]; ValueName
0x180026a37  mov     r8d, eax
0x180026a3a  call    BipWriteRegUlong
0x180026a3f  mov     ebx, eax
0x180026a41  test    eax, eax
0x180026a43  js      loc_180026AFB
0x180026a49  lea     rdx, aPackageflags; "PackageFlags"
0x180026a50  lea     rcx, [rbp+ValueName]; DestinationString
0x180026a54  call    cs:__imp_RtlInitUnicodeString
0x180026a5a  mov     r8, [rdi+50h]
0x180026a5e  lea     rdx, [rbp+ValueName]; ValueName
0x180026a62  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180026a66  mov     r8d, [r8+238h]
0x180026a6d  call    BipWriteRegUlong
0x180026a72  mov     ebx, eax
0x180026a74  test    eax, eax
0x180026a76  jns     loc_1800269A5
0x180026a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a83  test    byte ptr [rcx+1Ch], 8
0x180026a87  jz      loc_1800269A5
0x180026a8d  cmp     byte ptr [rcx+19h], 2
0x180026a91  jb      loc_1800269A5
0x180026a97  mov     edx, 56h ; 'V'
0x180026a9c  mov     rcx, [rcx+10h]
0x180026aa0  lea     r8, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids
0x180026aa7  mov     r9d, eax
0x180026aaa  call    WPP_SF_d
0x180026aaf  jmp     loc_1800269A5
0x180026ab4  mov     rcx, cs:BipHeap; HeapHandle
0x180026abb  xor     edx, edx; Flags
0x180026abd  call    cs:__imp_RtlFreeHeap
0x180026ac3  jmp     loc_1800269B2
0x180026ac8  cmp     byte ptr [rcx+19h], 2
0x180026acc  jb      loc_1800269A5
0x180026ad2  mov     edx, 52h ; 'R'
0x180026ad7  jmp     short loc_180026A9C
0x180026ad9  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ae0  test    byte ptr [rcx+1Ch], 8
0x180026ae4  jz      loc_1800269A5
0x180026aea  cmp     byte ptr [rcx+19h], 2
0x180026aee  jb      loc_1800269A5
0x180026af4  mov     edx, 54h ; 'T'
0x180026af9  jmp     short loc_180026A9C
0x180026afb  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b02  test    byte ptr [rcx+1Ch], 8
0x180026b06  jz      loc_1800269A5
0x180026b0c  cmp     byte ptr [rcx+19h], 2
0x180026b10  jb      loc_1800269A5
0x180026b16  mov     edx, 55h ; 'U'
0x180026b1b  jmp     loc_180026A9C
```
