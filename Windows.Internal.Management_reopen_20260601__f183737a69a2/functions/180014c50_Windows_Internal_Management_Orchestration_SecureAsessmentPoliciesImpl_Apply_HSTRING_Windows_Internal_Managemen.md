# Windows::Internal::Management::Orchestration::SecureAsessmentPoliciesImpl::Apply(HSTRING__ *,Windows::Internal::Management::Orchestration::SecureAssessmentPolicyTypes)

- ea: `0x180014c50`
- end: `0x180014cfe`
- name: `?Apply@SecureAsessmentPoliciesImpl@Orchestration@Management@Internal@Windows@@UEAAJPEAUHSTRING__@@W4SecureAssessmentPolicyTypes@2345@@Z`
- size: `174`
- prototype: `int __high(HSTRING, enum Windows::Internal::Management::Orchestration::SecureAssessmentPolicyTypes)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x18000a5c4`
- `0x180014c50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014c7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014c7a`
- `DMProcessXMLFiltered!MdmProcessConfigXmlWithAttributes` at `0x180014cc1`
- `DMProcessXMLFiltered!MdmProcessConfigXmlWithAttributes` at `0x180014cc1`

## string_xrefs

- `0x180014c99`: `\n<?xml version="1.0" encoding="utf-8" standalone="yes"?>\n<wap-provisioningdoc>\n    <characteristic type="Policy">\n        <characteristic type="Config">\n            <characteristic type="TextInput">\n                <parm name="AllowKeyboardTextSuggestions" value="0" datatype="integer"/>\n            </characteristic>\n        </characteristic>\n    </characteristic>\n</wap-provisioningdoc>\n`
- `0x180014ca2`: `\n<?xml version="1.0" encoding="utf-8" standalone="yes"?>\n<wap-provisioningdoc>\n    <characteristic type="Policy">\n        <characteristic type="Config">\n            <characteristic type="TextInput">\n                <parm name="AllowKeyboardTextSuggestions" value="1" datatype="integer"/>\n            </characteristic>\n        </characteristic>\n    </characteristic>\n</wap-provisioningdoc>\n`
- `0x180014cab`: `\n<?xml version="1.0" encoding="utf-8" standalone="yes"?>\n<wap-provisioningdoc>\n    <characteristic type="Policy">\n        <characteristic type="Config">\n            <characteristic type="AboveLock">\n                <parm name="AllowToasts" value="0" datatype="integer"/>\n            </characteristic>\n            <characteristic type="TextInput">\n                <parm name="AllowKeyboardTextSuggestions" value="0" datatype="integer"/>\n            </characteristic>\n            <characteri`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Management::Orchestration::SecureAsessmentPoliciesImpl::Apply(
        __int64 a1,
        HSTRING a2,
        int a3)
{
  const wchar_t *v4; // rdi
  int v5; // ebx
  int v6; // eax
  unsigned int v7; // ebx
  int v9[2]; // [rsp+20h] [rbp-18h] BYREF
  PCWSTR StringRawBuffer; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)v9 = L"OMADM::AccountID";
  v4 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  if ( a3 )
  {
    v5 = a3 - 1;
    if ( v5 )
    {
      if ( v5 == 1 )
        v4 = L"\n"
              "<?xml version=\"1.0\" encoding=\"utf-8\" standalone=\"yes\"?>\n"
              "<wap-provisioningdoc>\n"
              "    <characteristic type=\"Policy\">\n"
              "        <characteristic type=\"Config\">\n"
              "            <characteristic type=\"TextInput\">\n"
              "                <parm name=\"AllowKeyboardTextSuggestions\" value=\"0\" datatype=\"integer\"/>\n"
              "            </characteristic>\n"
              "        </characteristic>\n"
              "    </characteristic>\n"
              "</wap-provisioningdoc>\n";
    }
    else
    {
      v4 = L"\n"
            "<?xml version=\"1.0\" encoding=\"utf-8\" standalone=\"yes\"?>\n"
            "<wap-provisioningdoc>\n"
            "    <characteristic type=\"Policy\">\n"
            "        <characteristic type=\"Config\">\n"
            "            <characteristic type=\"TextInput\">\n"
            "                <parm name=\"AllowKeyboardTextSuggestions\" value=\"1\" datatype=\"integer\"/>\n"
            "            </characteristic>\n"
            "        </characteristic>\n"
            "    </characteristic>\n"
            "</wap-provisioningdoc>\n";
    }
  }
  else
  {
    v4 = L"\n"
          "<?xml version=\"1.0\" encoding=\"utf-8\" standalone=\"yes\"?>\n"
          "<wap-provisioningdoc>\n"
          "    <characteristic type=\"Policy\">\n"
          "        <characteristic type=\"Config\">\n"
          "            <characteristic type=\"AboveLock\">\n"
          "                <parm name=\"AllowToasts\" value=\"0\" datatype=\"integer\"/>\n"
          "            </characteristic>\n"
          "            <characteristic type=\"TextInput\">\n"
          "                <parm name=\"AllowKeyboardTextSuggestions\" value=\"0\" datatype=\"integer\"/>\n"
          "            </characteristic>\n"
          "            <characteristic type=\"ApplicationManagement\">\n"
          "                <parm name=\"AllowAppStoreAutoUpdate\" value=\"0\" datatype=\"integer\"/>\n"
          "            </characteristic>\n"
          "            <characteristic type=\"Experience\">\n"
          "                <parm name=\"AllowDeviceDiscovery\" value=\"0\" datatype=\"integer\"/>\n"
          "            </characteristic>\n"
          "            <characteristic type=\"Experience\">\n"
          "                <parm name=\"AllowCortana\" value=\"0\" datatype=\"integer\"/>\n"
          "            </characteristic>\n"
          "            <characteristic type=\"Update\">\n"
          "                <parm name=\"AllowAutoUpdate\" value=\"0\" datatype=\"integer\"/>\n"
          "            </characteristic>\n"
          "        </characteristic>\n"
          "    </characteristic>\n"
          "</wap-provisioningdoc>\n";
  }
  v6 = MdmProcessConfigXmlWithAttributes(v4, 1, v9);
  v7 = v6;
  if ( v6 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6E,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\secureassessmentpolicies.cpp",
    (const char *)(unsigned int)v6,
    v9[0]);
  return v7;
}

```

## disassembly

```asm
0x180014c50  mov     [rsp+arg_0], rbx
0x180014c55  push    rdi
0x180014c56  sub     rsp, 30h
0x180014c5a  xor     ecx, ecx
0x180014c5c  mov     rax, rdx
0x180014c5f  mov     [rsp+38h+var_10], rcx
0x180014c64  xor     edx, edx; length
0x180014c66  lea     rcx, aOmadmAccountid; "OMADM::AccountID"
0x180014c6d  mov     ebx, r8d
0x180014c70  mov     qword ptr [rsp+38h+var_18], rcx; int
0x180014c75  xor     edi, edi
0x180014c77  mov     rcx, rax; string
0x180014c7a  call    cs:__imp_WindowsGetStringRawBuffer
0x180014c81  nop     dword ptr [rax+rax+00h]
0x180014c86  mov     [rsp+38h+var_10], rax
0x180014c8b  test    ebx, ebx
0x180014c8d  jz      short loc_180014CAB
0x180014c8f  sub     ebx, 1
0x180014c92  jz      short loc_180014CA2
0x180014c94  cmp     ebx, 1
0x180014c97  jnz     short loc_180014CB2
0x180014c99  lea     rdi, aXmlVersion10En; "\n<?xml version=\"1.0\" encoding=\"utf-"...
0x180014ca0  jmp     short loc_180014CB2
0x180014ca2  lea     rdi, aXmlVersion10En_0; "\n<?xml version=\"1.0\" encoding=\"utf-"...
0x180014ca9  jmp     short loc_180014CB2
0x180014cab  lea     rdi, aXmlVersion10En_1; "\n<?xml version=\"1.0\" encoding=\"utf-"...
0x180014cb2  xor     r9d, r9d
0x180014cb5  lea     r8, [rsp+38h+var_18]
0x180014cba  mov     rcx, rdi
0x180014cbd  lea     edx, [r9+1]
0x180014cc1  call    cs:__imp_MdmProcessConfigXmlWithAttributes
0x180014cc8  nop     dword ptr [rax+rax+00h]
0x180014ccd  mov     ebx, eax
0x180014ccf  test    eax, eax
0x180014cd1  jns     short loc_180014CF0
0x180014cd3  mov     rcx, [rsp+38h]; this
0x180014cd8  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180014cdf  mov     r9d, eax; char *
0x180014ce2  mov     edx, 6Eh ; 'n'; void *
0x180014ce7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014cec  mov     eax, ebx
0x180014cee  jmp     short loc_180014CF2
0x180014cf0  xor     eax, eax
0x180014cf2  mov     rbx, [rsp+38h+arg_0]
0x180014cf7  add     rsp, 30h
0x180014cfb  pop     rdi
0x180014cfc  retn
```
