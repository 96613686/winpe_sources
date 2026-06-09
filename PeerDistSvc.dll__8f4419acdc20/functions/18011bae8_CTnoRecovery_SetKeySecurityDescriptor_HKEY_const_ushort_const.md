# CTnoRecovery::SetKeySecurityDescriptor(HKEY__ * const,ushort const *)

- ea: `0x18011bae8`
- end: `0x18011bc09`
- name: `?SetKeySecurityDescriptor@CTnoRecovery@@SAJQEAUHKEY__@@PEBG@Z`
- size: `289`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026514`

## callees

- `0x18000cf48`
- `0x18001fc30`
- `0x18011b0b4`
- `0x18011bae8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011bb29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011bb29`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18011bb1f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18011bb1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011bb96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011bba5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011bbf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011bb96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011bba5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011bbf3`

## pseudocode

```c
__int64 __fastcall CTnoRecovery::SetKeySecurityDescriptor(HKEY hKey, LPCWSTR StringSecurityDescriptor)
{
  int v3; // edi
  PSECURITY_DESCRIPTOR v4; // rcx
  DWORD LastError; // eax
  signed int v6; // ebx
  int v7; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp+8h] BYREF

  v3 = (int)StringSecurityDescriptor;
  v4 = 0;
  SecurityDescriptor = 0;
  if ( hKey && StringSecurityDescriptor )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          18,
          (unsigned int)WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids,
          v3,
          LastError);
      }
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_12;
    }
    v7 = CTnoRecovery::ApplyNewSecurityDescriptorToKey(hKey, SecurityDescriptor);
    if ( v7 < 0 )
    {
      v6 = v7;
LABEL_12:
      LocalFree(SecurityDescriptor);
      return (unsigned int)v6;
    }
    LocalFree(SecurityDescriptor);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        17,
        WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids,
        hKey,
        StringSecurityDescriptor);
      v4 = SecurityDescriptor;
    }
    LocalFree(v4);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18011bae8  mov     [rsp+arg_8], rbx
0x18011baed  push    rdi
0x18011baee  sub     rsp, 30h
0x18011baf2  mov     rbx, rcx
0x18011baf5  mov     rdi, rdx
0x18011baf8  xor     ecx, ecx
0x18011bafa  mov     [rsp+38h+SecurityDescriptor], rcx
0x18011baff  test    rbx, rbx
0x18011bb02  jz      loc_18011BBAF
0x18011bb08  test    rdx, rdx
0x18011bb0b  jz      loc_18011BBAF
0x18011bb11  lea     edx, [rcx+1]; StringSDRevision
0x18011bb14  xor     r9d, r9d; SecurityDescriptorSize
0x18011bb17  mov     rcx, rdi; StringSecurityDescriptor
0x18011bb1a  lea     r8, [rsp+38h+SecurityDescriptor]; SecurityDescriptor
0x18011bb1f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18011bb25  test    eax, eax
0x18011bb27  jnz     short loc_18011BB7E
0x18011bb29  call    cs:__imp_GetLastError
0x18011bb2f  mov     ebx, eax
0x18011bb31  mov     rcx, cs:WPP_GLOBAL_Control
0x18011bb38  lea     rdx, WPP_GLOBAL_Control
0x18011bb3f  cmp     rcx, rdx
0x18011bb42  jz      short loc_18011BB6F
0x18011bb44  test    dword ptr [rcx+6Ch], 8000000h
0x18011bb4b  jz      short loc_18011BB6F
0x18011bb4d  cmp     byte ptr [rcx+69h], 1
0x18011bb51  jb      short loc_18011BB6F
0x18011bb53  mov     rcx, [rcx+60h]
0x18011bb57  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011bb5e  mov     edx, 12h
0x18011bb63  mov     dword ptr [rsp+38h+var_18], eax
0x18011bb67  mov     r9, rdi
0x18011bb6a  call    WPP_SF_Sd
0x18011bb6f  test    ebx, ebx
0x18011bb71  jle     short loc_18011BB91
0x18011bb73  movzx   ebx, bx
0x18011bb76  or      ebx, 80070000h
0x18011bb7c  jmp     short loc_18011BB91
0x18011bb7e  mov     rdx, [rsp+38h+SecurityDescriptor]; pSecurityDescriptor
0x18011bb83  mov     rcx, rbx; hKey
0x18011bb86  call    ?ApplyNewSecurityDescriptorToKey@CTnoRecovery@@CAJPEAUHKEY__@@PEAX@Z; CTnoRecovery::ApplyNewSecurityDescriptorToKey(HKEY__ *,void *)
0x18011bb8b  test    eax, eax
0x18011bb8d  jns     short loc_18011BBA0
0x18011bb8f  mov     ebx, eax
0x18011bb91  mov     rcx, [rsp+38h+SecurityDescriptor]; hMem
0x18011bb96  call    cs:__imp_LocalFree
0x18011bb9c  mov     eax, ebx
0x18011bb9e  jmp     short loc_18011BBFE
0x18011bba0  mov     rcx, [rsp+38h+SecurityDescriptor]; hMem
0x18011bba5  call    cs:__imp_LocalFree
0x18011bbab  xor     eax, eax
0x18011bbad  jmp     short loc_18011BBFE
0x18011bbaf  mov     rax, cs:WPP_GLOBAL_Control
0x18011bbb6  lea     rdx, WPP_GLOBAL_Control
0x18011bbbd  cmp     rax, rdx
0x18011bbc0  jz      short loc_18011BBF3
0x18011bbc2  test    dword ptr [rax+6Ch], 8000000h
0x18011bbc9  jz      short loc_18011BBF3
0x18011bbcb  cmp     byte ptr [rax+69h], 1
0x18011bbcf  jb      short loc_18011BBF3
0x18011bbd1  mov     rcx, [rax+60h]
0x18011bbd5  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011bbdc  mov     edx, 11h
0x18011bbe1  mov     [rsp+38h+var_18], rdi
0x18011bbe6  mov     r9, rbx
0x18011bbe9  call    WPP_SF_qq
0x18011bbee  mov     rcx, [rsp+38h+SecurityDescriptor]; hMem
0x18011bbf3  call    cs:__imp_LocalFree
0x18011bbf9  mov     eax, 80070057h
0x18011bbfe  mov     rbx, [rsp+38h+arg_8]
0x18011bc03  add     rsp, 30h
0x18011bc07  pop     rdi
0x18011bc08  retn
```
