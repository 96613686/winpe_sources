# RegisterRpcInterfaces(void * *)

- ea: `0x180001730`
- end: `0x18000187b`
- name: `?RegisterRpcInterfaces@@YAJPEAPEAX@Z`
- size: `331`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005f00`

## callees

- `0x180001730`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001867`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000175b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000175b`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000182f`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000182f`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000183e`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000183e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000184e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000184e`

## string_xrefs

- `0x180001795`: `LicenseServiceEndpoint`

## pseudocode

```c
signed int __fastcall RegisterRpcInterfaces(void **a1)
{
  int v2; // ebx
  signed int result; // eax
  _QWORD v4[6]; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v5[2]; // [rsp+70h] [rbp-58h] BYREF
  __int128 v6; // [rsp+80h] [rbp-48h]
  int v7; // [rsp+90h] [rbp-38h]
  int v8; // [rsp+94h] [rbp-34h]
  __int64 v9; // [rsp+98h] [rbp-30h]
  __int64 (__fastcall *v10)(WARBIRD_DELAY_LOAD *__hidden, HDC, int); // [rsp+A0h] [rbp-28h]
  __int64 v11; // [rsp+A8h] [rbp-20h]
  const WCHAR *v12; // [rsp+B0h] [rbp-18h]
  HLOCAL v13; // [rsp+B8h] [rbp-10h]
  HLOCAL hMem; // [rsp+D8h] [rbp+10h] BYREF

  hMem = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)",
         1u,
         &hMem,
         0) )
  {
    v5[1] = qword_180019000;
    v4[1] = L"ncalrpc";
    v12 = L"LicenseManager";
    v4[2] = L"LicenseServiceEndpoint";
    v10 = WARBIRD_DELAY_LOAD::SetBkMode;
    v13 = hMem;
    v4[3] = hMem;
    v5[0] = 0;
    v6 = 0;
    v9 = 0;
    v11 = 0;
    v7 = 32;
    v8 = 1234;
    v4[0] = 0;
    v4[4] = 10;
    v2 = RpcServerInterfaceGroupCreateW(v5, 1, v4);
    if ( v2 >= 0 )
      v2 = RpcServerInterfaceGroupActivate(*a1);
    LocalFree(hMem);
    return v2;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180001730  mov     rax, rsp
0x180001733  mov     [rax+8], rbx
0x180001737  push    rdi
0x180001738  sub     rsp, 0C0h
0x18000173f  mov     rdi, rcx
0x180001742  lea     r8, [rax+10h]; SecurityDescriptor
0x180001746  xor     ebx, ebx
0x180001748  lea     rcx, StringSecurityDescriptor; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18000174f  xor     r9d, r9d; SecurityDescriptorSize
0x180001752  mov     [rax+10h], rbx
0x180001756  mov     edx, 1; StringSDRevision
0x18000175b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180001761  test    eax, eax
0x180001763  jz      loc_180001867
0x180001769  mov     [rsp+0C8h+var_90], rdi
0x18000176e  lea     rax, qword_180019000
0x180001775  mov     [rsp+0C8h+var_50], rax
0x18000177a  lea     rcx, aNcalrpc; "ncalrpc"
0x180001781  mov     [rsp+0C8h+var_80], rcx
0x180001786  lea     rax, ServiceName; "LicenseManager"
0x18000178d  mov     [rsp+0C8h+var_18], rax
0x180001795  lea     rcx, aLicenseservice; "LicenseServiceEndpoint"
0x18000179c  lea     rax, ?SetBkMode@WARBIRD_DELAY_LOAD@@YAHPEAUHDC__@@H@Z; WARBIRD_DELAY_LOAD::SetBkMode(HDC__ *,int)
0x1800017a3  mov     [rsp+0C8h+var_78], rcx
0x1800017a8  mov     [rsp+0C8h+var_28], rax
0x1800017b0  lea     r8, [rsp+0C8h+var_88]
0x1800017b5  mov     rax, [rsp+0C8h+hMem]
0x1800017bd  lea     rcx, [rsp+0C8h+var_58]
0x1800017c2  mov     r9d, 1
0x1800017c8  mov     [rsp+0C8h+var_98], rbx
0x1800017cd  xorps   xmm0, xmm0
0x1800017d0  mov     [rsp+0C8h+var_A0], rbx
0x1800017d5  mov     edx, r9d
0x1800017d8  mov     [rsp+0C8h+var_10], rax
0x1800017e0  mov     [rsp+0C8h+var_70], rax
0x1800017e5  mov     [rsp+0C8h+var_58], rbx
0x1800017ea  movdqa  [rsp+0C8h+var_48], xmm0
0x1800017f3  mov     [rsp+0C8h+var_30], rbx
0x1800017fb  mov     [rsp+0C8h+var_20], rbx
0x180001803  mov     [rsp+0C8h+var_38], 20h ; ' '
0x18000180e  mov     [rsp+0C8h+var_34], 4D2h
0x180001819  mov     [rsp+0C8h+var_88], rbx
0x18000181e  mov     [rsp+0C8h+var_68], 0Ah
0x180001827  mov     [rsp+0C8h+var_A8], 0FFFFFFFFh
0x18000182f  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x180001835  mov     ebx, eax
0x180001837  test    eax, eax
0x180001839  js      short loc_180001846
0x18000183b  mov     rcx, [rdi]
0x18000183e  call    cs:__imp_RpcServerInterfaceGroupActivate
0x180001844  mov     ebx, eax
0x180001846  mov     rcx, [rsp+0C8h+hMem]; hMem
0x18000184e  call    cs:__imp_LocalFree
0x180001854  mov     eax, ebx
0x180001856  mov     rbx, [rsp+0C8h+arg_0]
0x18000185e  add     rsp, 0C0h
0x180001865  pop     rdi
0x180001866  retn
0x180001867  call    cs:__imp_GetLastError
0x18000186d  test    eax, eax
0x18000186f  jle     short loc_180001856
0x180001871  movzx   eax, ax
0x180001874  or      eax, 80070000h
0x180001879  jmp     short loc_180001856
```
