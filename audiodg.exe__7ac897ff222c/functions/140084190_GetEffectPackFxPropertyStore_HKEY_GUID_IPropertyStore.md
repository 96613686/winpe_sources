# GetEffectPackFxPropertyStore(HKEY__ *,_GUID,IPropertyStore * *)

- ea: `0x140084190`
- end: `0x140084324`
- name: `?GetEffectPackFxPropertyStore@@YAJPEAUHKEY__@@U_GUID@@PEAPEAUIPropertyStore@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(HKEY hKey, struct _GUID *__struct_ptr, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140052090`

## callees

- `0x14000c33c`
- `0x140018e68`
- `0x14003c290`
- `0x14005d0e0`
- `0x1400690a0`
- `0x140084190`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14008428a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14008428a`
- `MMDevAPI!__imp_MMDeviceCreateRegistryPropertyStore2` at `0x1400842c5`
- `MMDevAPI!__imp_MMDeviceCreateRegistryPropertyStore2` at `0x1400842c5`

## pseudocode

```c
__int64 __fastcall GetEffectPackFxPropertyStore(HKEY hKey, struct _GUID *a2, struct IPropertyStore **a3)
{
  int Data2; // esi
  int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  HKEY v9; // rcx
  int RegistryPropertyStore2; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-298h]
  HKEY v13[2]; // [rsp+70h] [rbp-248h] BYREF
  WCHAR SubKey[256]; // [rsp+80h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  Data2 = a2->Data2;
  *a3 = 0;
  v6 = StringCchPrintfW(
         SubKey,
         0x100u,
         L"EffectPackRegistration\\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}\\FxProperties",
         a2->Data1);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v13[0] = 0;
    v8 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, v13);
    if ( v8 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x46,
             (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\effectpackutil.cpp",
             (const char *)v8,
             phkResult);
    }
    else
    {
      v9 = v13[0];
      v13[0] = 0;
      RegistryPropertyStore2 = MMDeviceCreateRegistryPropertyStore2(v9, a3);
      v7 = RegistryPropertyStore2;
      if ( RegistryPropertyStore2 >= 0 )
        v7 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\effectpackutil.cpp",
          (const char *)(unsigned int)RegistryPropertyStore2,
          phkResult);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v13);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\effectpackutil.cpp",
      (const char *)(unsigned int)v6,
      Data2);
  }
  return v7;
}

```

## disassembly

```asm
0x140084190  mov     [rsp+arg_18], rbx
0x140084195  push    rbp
0x140084196  push    rsi
0x140084197  push    rdi
0x140084198  push    r14
0x14008419a  push    r15
0x14008419c  sub     rsp, 290h
0x1400841a3  mov     rax, cs:__security_cookie
0x1400841aa  xor     rax, rsp
0x1400841ad  mov     [rsp+2B8h+var_38], rax
0x1400841b5  movzx   r9d, byte ptr [rdx+0Ch]
0x1400841ba  mov     r14, rdx
0x1400841bd  movzx   eax, byte ptr [rdx+0Fh]
0x1400841c1  mov     rbp, rcx
0x1400841c4  movzx   ecx, byte ptr [rdx+0Eh]
0x1400841c8  mov     r15, r8
0x1400841cb  mov     [rsp+2B8h+var_250], eax
0x1400841cf  movzx   r10d, byte ptr [r14+0Ah]
0x1400841d4  movzx   r11d, byte ptr [r14+9]
0x1400841d9  movzx   ebx, byte ptr [r14+8]
0x1400841de  movzx   edi, word ptr [r14+6]
0x1400841e3  movzx   esi, word ptr [r14+4]
0x1400841e8  mov     [rsp+2B8h+var_258], ecx
0x1400841ec  lea     rcx, [rsp+2B8h+SubKey]; unsigned __int16 *
0x1400841f4  mov     qword ptr [r8], 0
0x1400841fb  movzx   r8d, byte ptr [rdx+0Dh]
0x140084200  movzx   edx, byte ptr [rdx+0Bh]
0x140084204  mov     [rsp+2B8h+var_260], r8d
0x140084209  lea     r8, aEffectpackregi; "EffectPackRegistration\\{%08x-%04x-%04x"...
0x140084210  mov     [rsp+2B8h+var_268], r9d
0x140084215  mov     r9d, [r14]
0x140084218  mov     [rsp+2B8h+var_270], edx
0x14008421c  mov     edx, 100h; unsigned __int64
0x140084221  mov     [rsp+2B8h+var_278], r10d
0x140084226  mov     [rsp+2B8h+var_280], r11d
0x14008422b  mov     [rsp+2B8h+var_288], ebx
0x14008422f  mov     [rsp+2B8h+var_290], edi
0x140084233  mov     dword ptr [rsp+2B8h+phkResult], esi; int
0x140084237  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14008423c  mov     ebx, eax
0x14008423e  test    eax, eax
0x140084240  jns     short loc_140084263
0x140084242  mov     rcx, [rsp+2B8h]; this
0x14008424a  lea     r8, aAvcoreAudiocor_72; "avcore\\audiocore\\server\\lib\\audioen"...
0x140084251  mov     r9d, eax; char *
0x140084254  mov     edx, 43h ; 'C'; void *
0x140084259  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008425e  jmp     loc_1400842FB
0x140084263  lea     rax, [rsp+2B8h+var_248]
0x140084268  mov     [rsp+2B8h+var_248], 0
0x140084271  mov     r9d, 20019h; samDesired
0x140084277  mov     [rsp+2B8h+phkResult], rax; int
0x14008427c  xor     r8d, r8d; ulOptions
0x14008427f  lea     rdx, [rsp+2B8h+SubKey]; lpSubKey
0x140084287  mov     rcx, rbp; hKey
0x14008428a  call    cs:__imp_RegOpenKeyExW
0x140084290  test    eax, eax
0x140084292  jz      short loc_1400842B4
0x140084294  mov     rcx, [rsp+2B8h]; this
0x14008429c  lea     r8, aAvcoreAudiocor_72; "avcore\\audiocore\\server\\lib\\audioen"...
0x1400842a3  mov     r9d, eax; char *
0x1400842a6  mov     edx, 46h ; 'F'; void *
0x1400842ab  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400842b0  mov     ebx, eax
0x1400842b2  jmp     short loc_1400842F1
0x1400842b4  mov     rcx, [rsp+2B8h+var_248]
0x1400842b9  mov     rdx, r15
0x1400842bc  mov     [rsp+2B8h+var_248], 0
0x1400842c5  call    cs:__imp_MMDeviceCreateRegistryPropertyStore2
0x1400842cb  mov     ebx, eax
0x1400842cd  test    eax, eax
0x1400842cf  jns     short loc_1400842EF
0x1400842d1  mov     rcx, [rsp+2B8h]; this
0x1400842d9  lea     r8, aAvcoreAudiocor_72; "avcore\\audiocore\\server\\lib\\audioen"...
0x1400842e0  mov     r9d, eax; char *
0x1400842e3  mov     edx, 48h ; 'H'; void *
0x1400842e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400842ed  jmp     short loc_1400842F1
0x1400842ef  xor     ebx, ebx
0x1400842f1  lea     rcx, [rsp+2B8h+var_248]
0x1400842f6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400842fb  mov     eax, ebx
0x1400842fd  mov     rcx, [rsp+2B8h+var_38]
0x140084305  xor     rcx, rsp; StackCookie
0x140084308  call    __security_check_cookie
0x14008430d  mov     rbx, [rsp+2B8h+arg_18]
0x140084315  add     rsp, 290h
0x14008431c  pop     r15
0x14008431e  pop     r14
0x140084320  pop     rdi
0x140084321  pop     rsi
0x140084322  pop     rbp
0x140084323  retn
```
