# CalRpcCreateAppContainerRpcSD(void * *)

- ea: `0x180015604`
- end: `0x180015689`
- name: `?CalRpcCreateAppContainerRpcSD@@YAKPEAPEAX@Z`
- size: `133`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *SecurityDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800186d0`

## callees

- `0x1800075d0`
- `0x180015604`
- `0x18002ab90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001562c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001562c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180015622`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180015622`

## pseudocode

```c
__int64 __fastcall CalRpcCreateAppContainerRpcSD(PSECURITY_DESCRIPTOR *SecurityDescriptor)
{
  DWORD LastError; // ebx
  __int64 v2; // rcx

  *SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GR;;;AN)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;S-1-15-3-9)",
         1u,
         SecurityDescriptor,
         0) )
  {
    return 0;
  }
  LastError = GetLastError();
  WppTraceIndent(v2, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_8fae02f726263adb5326c29facded416_Traceguids,
      (_DWORD)WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180015604  push    rbx
0x180015606  sub     rsp, 30h
0x18001560a  xor     r9d, r9d; SecurityDescriptorSize
0x18001560d  mov     qword ptr [rcx], 0
0x180015614  mov     r8, rcx; SecurityDescriptor
0x180015617  lea     rcx, StringSecurityDescriptor; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18001561e  lea     edx, [r9+1]; StringSDRevision
0x180015622  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180015628  test    eax, eax
0x18001562a  jnz     short loc_180015681
0x18001562c  call    cs:__imp_GetLastError
0x180015632  mov     edx, 2
0x180015637  mov     ebx, eax
0x180015639  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001563e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015645  lea     rax, WPP_GLOBAL_Control
0x18001564c  cmp     rcx, rax
0x18001564f  jz      short loc_18001567D
0x180015651  test    byte ptr [rcx+1Ch], 20h
0x180015655  jz      short loc_18001567D
0x180015657  cmp     byte ptr [rcx+19h], 2
0x18001565b  jb      short loc_18001567D
0x18001565d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180015664  lea     r8, WPP_8fae02f726263adb5326c29facded416_Traceguids
0x18001566b  mov     rcx, [rcx+10h]
0x18001566f  mov     edx, 0Ah
0x180015674  mov     [rsp+38h+var_18], ebx
0x180015678  call    WPP_SF_sD
0x18001567d  mov     eax, ebx
0x18001567f  jmp     short loc_180015683
0x180015681  xor     eax, eax
0x180015683  add     rsp, 30h
0x180015687  pop     rbx
0x180015688  retn
```
