# CBrowserBrokerInstance::GetAppContainerFolderPermissions(ushort const *,ushort * *)

- ea: `0x180008ec0`
- end: `0x180009029`
- name: `?GetAppContainerFolderPermissions@CBrowserBrokerInstance@@UEAAJPEBGPEAPEAG@Z`
- size: `361`
- prototype: `int(CBrowserBrokerInstance *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180008ec0`
- `0x18000a2dc`
- `0x18000e428`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180008fd0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180008fd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009005`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009005`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008f74`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008f74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008fdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008fee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008fdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008fee`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180008f2e`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180008f2e`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180008f60`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180008f97`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180008f60`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180008f97`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180008fbf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180008fbf`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerInstance::GetAppContainerFolderPermissions(
        CBrowserBrokerInstance *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int PIC; // ebx
  void *File2; // rsi
  HLOCAL v7; // rdi
  LPWSTR StringSecurityDescriptor; // [rsp+30h] [rbp-30h] BYREF
  _OWORD v10[2]; // [rsp+38h] [rbp-28h] BYREF
  DWORD nLengthNeeded; // [rsp+98h] [rbp+38h] BYREF

  nLengthNeeded = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &nLengthNeeded);
  if ( PIC >= 0 )
  {
    memset(v10, 0, sizeof(v10));
    LODWORD(v10[0]) = 32;
    DWORD2(v10[0]) = 0x2000000;
    File2 = (void *)CreateFile2(a2, 0x80000000LL, 1, 3, v10);
    if ( File2 == (void *)-1LL )
    {
      return (unsigned int)-2147024809;
    }
    else
    {
      nLengthNeeded = 0;
      if ( GetKernelObjectSecurity(File2, 4u, 0, 0, &nLengthNeeded) )
      {
        PIC = -2147418113;
      }
      else
      {
        v7 = LocalAlloc(0x40u, nLengthNeeded);
        if ( v7 )
        {
          if ( GetKernelObjectSecurity(File2, 4u, v7, nLengthNeeded, &nLengthNeeded)
            && (StringSecurityDescriptor = 0,
                ConvertSecurityDescriptorToStringSecurityDescriptorW(v7, 1u, 4u, &StringSecurityDescriptor, 0)) )
          {
            PIC = SHStrDupW(StringSecurityDescriptor, a3);
            LocalFree(StringSecurityDescriptor);
          }
          else
          {
            PIC = HRESULTFromLastErrorError();
          }
          LocalFree(v7);
        }
        else
        {
          PIC = -2147024882;
        }
      }
      CloseHandle(File2);
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180008ec0  mov     [rsp-18h+arg_0], rbx
0x180008ec5  mov     [rsp-18h+arg_8], rsi
0x180008eca  push    rbp
0x180008ecb  push    rdi
0x180008ecc  push    r14
0x180008ece  mov     rbp, rsp
0x180008ed1  sub     rsp, 60h
0x180008ed5  mov     rdi, rdx
0x180008ed8  mov     [rbp+nLengthNeeded], 0
0x180008edf  lea     rdx, [rbp+nLengthNeeded]; unsigned int *
0x180008ee3  mov     ecx, 1; unsigned int
0x180008ee8  mov     r14, r8
0x180008eeb  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180008ef0  mov     ebx, eax
0x180008ef2  test    eax, eax
0x180008ef4  js      loc_180009012
0x180008efa  xorps   xmm0, xmm0
0x180008efd  lea     rax, [rbp+var_28]
0x180008f01  movups  [rbp+var_28], xmm0
0x180008f05  mov     r9d, 3
0x180008f0b  mov     dword ptr [rbp+var_28], 20h ; ' '
0x180008f12  mov     edx, 80000000h
0x180008f17  mov     dword ptr [rbp+var_28+8], 2000000h
0x180008f1e  mov     rcx, rdi
0x180008f21  mov     [rsp+60h+lpnLengthNeeded], rax
0x180008f26  movups  [rbp+var_18], xmm0
0x180008f2a  lea     r8d, [r9-2]
0x180008f2e  call    cs:__imp_CreateFile2
0x180008f34  mov     rsi, rax
0x180008f37  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008f3b  jz      loc_18000900D
0x180008f41  xor     r9d, r9d; nLength
0x180008f44  mov     [rbp+nLengthNeeded], 0
0x180008f4b  lea     rax, [rbp+nLengthNeeded]
0x180008f4f  xor     r8d, r8d; pSecurityDescriptor
0x180008f52  mov     rcx, rsi; Handle
0x180008f55  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180008f5a  lea     ebx, [r9+4]
0x180008f5e  mov     edx, ebx; RequestedInformation
0x180008f60  call    cs:__imp_GetKernelObjectSecurity
0x180008f66  test    eax, eax
0x180008f68  jnz     loc_180008FFD
0x180008f6e  mov     edx, [rbp+nLengthNeeded]; uBytes
0x180008f71  lea     ecx, [rbx+3Ch]; uFlags
0x180008f74  call    cs:__imp_LocalAlloc
0x180008f7a  mov     rdi, rax
0x180008f7d  test    rax, rax
0x180008f80  jz      short loc_180008FF6
0x180008f82  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180008f86  lea     rax, [rbp+nLengthNeeded]
0x180008f8a  mov     r8, rdi; pSecurityDescriptor
0x180008f8d  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180008f92  mov     edx, ebx; RequestedInformation
0x180008f94  mov     rcx, rsi; Handle
0x180008f97  call    cs:__imp_GetKernelObjectSecurity
0x180008f9d  test    eax, eax
0x180008f9f  jz      short loc_180008FE4
0x180008fa1  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x180008fa5  mov     [rbp+StringSecurityDescriptor], 0
0x180008fad  mov     r8d, ebx; SecurityInformation
0x180008fb0  mov     [rsp+60h+lpnLengthNeeded], 0; StringSecurityDescriptorLen
0x180008fb9  lea     edx, [rbx-3]; RequestedStringSDRevision
0x180008fbc  mov     rcx, rdi; SecurityDescriptor
0x180008fbf  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180008fc5  test    eax, eax
0x180008fc7  jz      short loc_180008FE4
0x180008fc9  mov     rcx, [rbp+StringSecurityDescriptor]; psz
0x180008fcd  mov     rdx, r14; ppwsz
0x180008fd0  call    cs:__imp_SHStrDupW
0x180008fd6  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x180008fda  mov     ebx, eax
0x180008fdc  call    cs:__imp_LocalFree
0x180008fe2  jmp     short loc_180008FEB
0x180008fe4  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180008fe9  mov     ebx, eax
0x180008feb  mov     rcx, rdi; hMem
0x180008fee  call    cs:__imp_LocalFree
0x180008ff4  jmp     short loc_180009002
0x180008ff6  mov     ebx, 8007000Eh
0x180008ffb  jmp     short loc_180009002
0x180008ffd  mov     ebx, 8000FFFFh
0x180009002  mov     rcx, rsi; hObject
0x180009005  call    cs:__imp_CloseHandle
0x18000900b  jmp     short loc_180009012
0x18000900d  mov     ebx, 80070057h
0x180009012  lea     r11, [rsp+60h+var_s0]
0x180009017  mov     eax, ebx
0x180009019  mov     rbx, [r11+20h]
0x18000901d  mov     rsi, [r11+28h]
0x180009021  mov     rsp, r11
0x180009024  pop     r14
0x180009026  pop     rdi
0x180009027  pop     rbp
0x180009028  retn
```
