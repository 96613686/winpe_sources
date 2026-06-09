# Microsoft::CoreUI::Messaging::NTSecurity::GetAppContainerNamedObjectPath(bool,CFlat::Ref<CFlat::SmartPtr<System::String>>)

- ea: `0x180072608`
- end: `0x1800726a4`
- name: `?GetAppContainerNamedObjectPath@NTSecurity@Messaging@CoreUI@Microsoft@@SA?AW4MessagingResults@234@_NU?$Ref@V?$SmartPtr@VString@System@@@CFlat@@@CFlat@@@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008c2c4`

## callees

- `0x180010ed0`
- `0x18002eb74`
- `0x18003950c`
- `0x180072608`
- `0x1800726ac`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18007268d`
- `ntdll!RtlFreeUnicodeString` at `0x18007268d`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x180072639`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x180072639`

## pseudocode

```c
__int64 __fastcall Microsoft::CoreUI::Messaging::NTSecurity::GetAppContainerNamedObjectPath(
        __int64 a1,
        System::Object **a2)
{
  System::Object *v2; // rcx
  int v4; // eax
  __int64 v5; // r8
  __int64 result; // rax
  __int64 v7; // rax
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF
  System::Object *v9; // [rsp+48h] [rbp+10h] BYREF

  v2 = *a2;
  *a2 = 0;
  if ( v2 )
    System::Object::Release$(v2);
  UnicodeString = 0;
  v4 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, struct _UNICODE_STRING *))RtlGetAppContainerNamedObjectPath)(
         0,
         0,
         0,
         &UnicodeString)
     | 0x10000000;
  if ( v4 < 0 )
    CFlat::Abandonment::FailWithHR(v4, 0, 0);
  result = 9;
  if ( UnicodeString.Buffer )
  {
    v7 = System::String::Create$(&v9, UnicodeString.Buffer, v5, UnicodeString.Length >> 1);
    CFlat::SmartPtr<System::Action>::operator=(a2, v7);
    if ( v9 )
      System::Object::Release$(v9);
    RtlFreeUnicodeString(&UnicodeString);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180072608  push    rbx
0x18007260a  sub     rsp, 30h
0x18007260e  mov     rcx, [rdx]; this
0x180072611  mov     rbx, rdx
0x180072614  mov     qword ptr [rdx], 0
0x18007261b  test    rcx, rcx
0x18007261e  jz      short loc_180072625
0x180072620  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180072625  xorps   xmm0, xmm0
0x180072628  lea     r9, [rsp+38h+UnicodeString]
0x18007262d  xor     r8d, r8d
0x180072630  xor     edx, edx
0x180072632  xor     ecx, ecx
0x180072634  movups  xmmword ptr [rsp+38h+UnicodeString.Length], xmm0
0x180072639  call    cs:__imp_RtlGetAppContainerNamedObjectPath
0x18007263f  or      eax, 10000000h
0x180072644  jl      short loc_180072697
0x180072646  mov     rdx, [rsp+38h+UnicodeString.Buffer]
0x18007264b  mov     eax, 9
0x180072650  test    rdx, rdx
0x180072653  jnz     short loc_18007265B
0x180072655  add     rsp, 30h
0x180072659  pop     rbx
0x18007265a  retn
0x18007265b  movzx   r9d, [rsp+38h+UnicodeString.Length]
0x180072661  lea     rcx, [rsp+38h+arg_8]
0x180072666  shr     r9d, 1
0x180072669  call    ?Create$@String@System@@SA?AV?$SmartPtr@VString@System@@@CFlat@@PEA_WHH@Z; System::String::Create$(wchar_t *,int,int)
0x18007266e  mov     rdx, rax
0x180072671  mov     rcx, rbx
0x180072674  call    ??4?$SmartPtr@VAction@System@@@CFlat@@QEAAAEAV01@$$QEAV01@@Z; CFlat::SmartPtr<System::Action>::operator=(CFlat::SmartPtr<System::Action> &&)
0x180072679  mov     rcx, [rsp+38h+arg_8]; this
0x18007267e  test    rcx, rcx
0x180072681  jz      short loc_180072688
0x180072683  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180072688  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18007268d  call    cs:__imp_RtlFreeUnicodeString
0x180072693  xor     eax, eax
0x180072695  jmp     short loc_180072655
0x180072697  xor     r8d, r8d; int
0x18007269a  xor     edx, edx; void *
0x18007269c  mov     ecx, eax; int
0x18007269e  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
```
