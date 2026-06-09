# Windows::Internal::Management::Orchestration::SecureAsessmentPoliciesImpl::Apply(HSTRING__ *,Windows::Internal::Management::Orchestration::SecureAssessmentPolicyTypes)

- ea: `0x180014570`
- end: `0x180014611`
- name: `?Apply@SecureAsessmentPoliciesImpl@Orchestration@Management@Internal@Windows@@UEAAJPEAUHSTRING__@@W4SecureAssessmentPolicyTypes@2345@@Z`
- size: `161`
- prototype: `int __high(HSTRING, enum Windows::Internal::Management::Orchestration::SecureAssessmentPolicyTypes)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x18000a2a4`
- `0x180014570`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001459a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001459a`
- `DMProcessXMLFiltered!MdmProcessConfigXmlWithAttributes` at `0x1800145db`
- `DMProcessXMLFiltered!MdmProcessConfigXmlWithAttributes` at `0x1800145db`

## string_xrefs

- `0x1800145b3`: `\n<?xml version="1.0" encoding="utf-8" standalone="yes"?>\n<wap-provisioningdoc>\n    <characteristic type="Policy">\n        <characteristic type="Config">\n            <characteristic type="TextInput">\n                <parm name="AllowKeyboardTextSuggestions" value="0" datatype="integer"/>\n            </characteristic>\n        </characteristic>\n    </characteristic>\n</wap-provisioningdoc>\n`
- `0x1800145bc`: `\n<?xml version="1.0" encoding="utf-8" standalone="yes"?>\n<wap-provisioningdoc>\n    <characteristic type="Policy">\n        <characteristic type="Config">\n            <characteristic type="TextInput">\n                <parm name="AllowKeyboardTextSuggestions" value="1" datatype="integer"/>\n            </characteristic>\n        </characteristic>\n    </characteristic>\n</wap-provisioningdoc>\n`
- `0x1800145c5`: `\n<?xml version="1.0" encoding="utf-8" standalone="yes"?>\n<wap-provisioningdoc>\n    <characteristic type="Policy">\n        <characteristic type="Config">\n            <characteristic type="AboveLock">\n                <parm name="AllowToasts" value="0" datatype="integer"/>\n            </characteristic>\n            <characteristic type="TextInput">\n                <parm name="AllowKeyboardTextSuggestions" value="0" datatype="integer"/>\n            </characteristic>\n            <characteri`

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
0x180014570  mov     [rsp+arg_0], rbx
0x180014575  push    rdi
0x180014576  sub     rsp, 30h
0x18001457a  xor     ecx, ecx
0x18001457c  mov     rax, rdx
0x18001457f  mov     [rsp+38h+var_10], rcx
0x180014584  xor     edx, edx; length
0x180014586  lea     rcx, aOmadmAccountid; "OMADM::AccountID"
0x18001458d  mov     ebx, r8d
0x180014590  mov     qword ptr [rsp+38h+var_18], rcx; int
0x180014595  xor     edi, edi
0x180014597  mov     rcx, rax; string
0x18001459a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800145a0  mov     [rsp+38h+var_10], rax
0x1800145a5  test    ebx, ebx
0x1800145a7  jz      short loc_1800145C5
0x1800145a9  sub     ebx, 1
0x1800145ac  jz      short loc_1800145BC
0x1800145ae  cmp     ebx, 1
0x1800145b1  jnz     short loc_1800145CC
0x1800145b3  lea     rdi, aXmlVersion10En; "\n<?xml version=\"1.0\" encoding=\"utf-"...
0x1800145ba  jmp     short loc_1800145CC
0x1800145bc  lea     rdi, aXmlVersion10En_0; "\n<?xml version=\"1.0\" encoding=\"utf-"...
0x1800145c3  jmp     short loc_1800145CC
0x1800145c5  lea     rdi, aXmlVersion10En_1; "\n<?xml version=\"1.0\" encoding=\"utf-"...
0x1800145cc  xor     r9d, r9d
0x1800145cf  lea     r8, [rsp+38h+var_18]
0x1800145d4  mov     rcx, rdi
0x1800145d7  lea     edx, [r9+1]
0x1800145db  call    cs:__imp_MdmProcessConfigXmlWithAttributes
0x1800145e1  mov     ebx, eax
0x1800145e3  test    eax, eax
0x1800145e5  jns     short loc_180014604
0x1800145e7  mov     rcx, [rsp+38h]; this
0x1800145ec  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800145f3  mov     r9d, eax; char *
0x1800145f6  mov     edx, 6Eh ; 'n'; void *
0x1800145fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014600  mov     eax, ebx
0x180014602  jmp     short loc_180014606
0x180014604  xor     eax, eax
0x180014606  mov     rbx, [rsp+38h+arg_0]
0x18001460b  add     rsp, 30h
0x18001460f  pop     rdi
0x180014610  retn
```
