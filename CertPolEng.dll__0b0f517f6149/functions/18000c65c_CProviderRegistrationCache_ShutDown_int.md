# CProviderRegistrationCache::ShutDown(int)

- ea: `0x18000c65c`
- end: `0x18000c7a9`
- name: `?ShutDown@CProviderRegistrationCache@@QEAAKH@Z`
- size: `333`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800043d0`
- `0x180013cb4`

## callees

- `0x18000b810`
- `0x18000c344`
- `0x18000c65c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c73b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c73b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c6a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c6a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c6f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c6f4`
- `CRYPT32!CertControlStore` at `0x18000c728`
- `CRYPT32!CertControlStore` at `0x18000c728`
- `CRYPT32!CertCloseStore` at `0x18000c6db`
- `CRYPT32!CertCloseStore` at `0x18000c765`
- `CRYPT32!CertCloseStore` at `0x18000c6db`
- `CRYPT32!CertCloseStore` at `0x18000c765`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18000c6c0`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18000c6c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c67e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c691`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c67e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c691`
- `ntdll!RtlDeleteResource` at `0x18000c77a`
- `ntdll!RtlDeleteResource` at `0x18000c77a`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::ShutDown(CProviderRegistrationCache *this, int a2)
{
  HKEY v4; // rcx
  HKEY v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  HANDLE *v11; // rdi
  DWORD LastError; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx

  if ( *((_DWORD *)this + 2) )
  {
    v4 = (HKEY)*((_QWORD *)this + 14);
    if ( v4 )
    {
      RegCloseKey(v4);
      *((_QWORD *)this + 14) = 0;
    }
    v5 = (HKEY)*((_QWORD *)this + 15);
    if ( v5 )
    {
      RegCloseKey(v5);
      *((_QWORD *)this + 15) = 0;
    }
    v6 = (void *)*((_QWORD *)this + 16);
    if ( v6 )
    {
      CloseHandle(v6);
      *((_QWORD *)this + 16) = 0;
    }
    v7 = (void *)*((_QWORD *)this + 17);
    if ( v7 )
    {
      CertFreeCertificateChainEngine(v7);
      *((_QWORD *)this + 17) = 0;
    }
    v8 = (void *)*((_QWORD *)this + 23);
    if ( v8 )
    {
      CertCloseStore(v8, 0);
      *((_QWORD *)this + 23) = 0;
    }
    v9 = (void *)*((_QWORD *)this + 21);
    if ( v9 )
    {
      LocalFree(v9);
      *((_QWORD *)this + 21) = 0;
    }
    v10 = (void *)*((_QWORD *)this + 41);
    *((_DWORD *)this + 44) = 0;
    if ( v10 )
    {
      v11 = (HANDLE *)((char *)this + 336);
      if ( *((_QWORD *)this + 42) )
      {
        if ( !CertControlStore(v10, 0, 5u, (char *)this + 336) && (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        {
          LastError = GetLastError();
          McTemplateU0sq_EtwEventWriteTransfer(v14, v13, "CertControlStore", LastError);
        }
        CloseHandle(*v11);
        *v11 = 0;
      }
      CertCloseStore(*((HCERTSTORE *)this + 41), 0);
      *((_QWORD *)this + 41) = 0;
    }
    if ( a2 )
    {
      RtlDeleteResource((PRTL_RESOURCE)((char *)this + 16));
      *((_DWORD *)this + 2) = 0;
    }
    else
    {
      CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>::RemoveAll((__int64)this + 144);
    }
    *((_QWORD *)this + 40) = 0;
    *((_DWORD *)this + 87) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c65c  push    rbx
0x18000c65e  push    rbp
0x18000c65f  push    rsi
0x18000c660  push    rdi
0x18000c661  sub     rsp, 28h
0x18000c665  xor     ebp, ebp
0x18000c667  mov     esi, edx
0x18000c669  mov     rbx, rcx
0x18000c66c  cmp     [rcx+8], ebp
0x18000c66f  jz      loc_18000C79E
0x18000c675  mov     rcx, [rcx+70h]; hKey
0x18000c679  test    rcx, rcx
0x18000c67c  jz      short loc_18000C688
0x18000c67e  call    cs:__imp_RegCloseKey
0x18000c684  mov     [rbx+70h], rbp
0x18000c688  mov     rcx, [rbx+78h]; hKey
0x18000c68c  test    rcx, rcx
0x18000c68f  jz      short loc_18000C69B
0x18000c691  call    cs:__imp_RegCloseKey
0x18000c697  mov     [rbx+78h], rbp
0x18000c69b  mov     rcx, [rbx+80h]; hObject
0x18000c6a2  test    rcx, rcx
0x18000c6a5  jz      short loc_18000C6B4
0x18000c6a7  call    cs:__imp_CloseHandle
0x18000c6ad  mov     [rbx+80h], rbp
0x18000c6b4  mov     rcx, [rbx+88h]; hChainEngine
0x18000c6bb  test    rcx, rcx
0x18000c6be  jz      short loc_18000C6CD
0x18000c6c0  call    cs:__imp_CertFreeCertificateChainEngine
0x18000c6c6  mov     [rbx+88h], rbp
0x18000c6cd  mov     rcx, [rbx+0B8h]; hCertStore
0x18000c6d4  test    rcx, rcx
0x18000c6d7  jz      short loc_18000C6E8
0x18000c6d9  xor     edx, edx; dwFlags
0x18000c6db  call    cs:__imp_CertCloseStore
0x18000c6e1  mov     [rbx+0B8h], rbp
0x18000c6e8  mov     rcx, [rbx+0A8h]; hMem
0x18000c6ef  test    rcx, rcx
0x18000c6f2  jz      short loc_18000C701
0x18000c6f4  call    cs:__imp_LocalFree
0x18000c6fa  mov     [rbx+0A8h], rbp
0x18000c701  mov     rcx, [rbx+148h]; hCertStore
0x18000c708  mov     [rbx+0B0h], ebp
0x18000c70e  test    rcx, rcx
0x18000c711  jz      short loc_18000C772
0x18000c713  lea     rdi, [rbx+150h]
0x18000c71a  cmp     [rdi], rbp
0x18000c71d  jz      short loc_18000C75C
0x18000c71f  xor     edx, edx; dwFlags
0x18000c721  mov     r9, rdi; pvCtrlPara
0x18000c724  lea     r8d, [rdx+5]; dwCtrlType
0x18000c728  call    cs:__imp_CertControlStore
0x18000c72e  test    eax, eax
0x18000c730  jnz     short loc_18000C750
0x18000c732  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000c739  jz      short loc_18000C750
0x18000c73b  call    cs:__imp_GetLastError
0x18000c741  mov     r9d, eax
0x18000c744  lea     r8, aCertcontrolsto; "CertControlStore"
0x18000c74b  call    McTemplateU0sq_EtwEventWriteTransfer
0x18000c750  mov     rcx, [rdi]; hObject
0x18000c753  call    cs:__imp_CloseHandle
0x18000c759  mov     [rdi], rbp
0x18000c75c  mov     rcx, [rbx+148h]; hCertStore
0x18000c763  xor     edx, edx; dwFlags
0x18000c765  call    cs:__imp_CertCloseStore
0x18000c76b  mov     [rbx+148h], rbp
0x18000c772  test    esi, esi
0x18000c774  jz      short loc_18000C785
0x18000c776  lea     rcx, [rbx+10h]; Resource
0x18000c77a  call    cs:__imp_RtlDeleteResource
0x18000c780  mov     [rbx+8], ebp
0x18000c783  jmp     short loc_18000C791
0x18000c785  lea     rcx, [rbx+90h]
0x18000c78c  call    ?RemoveAll@?$CPtrArrayTemplate@VCProviderEntry@@U?$AutoPtrTraits@VCProviderEntry@@@@@@QEAAXXZ; CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>::RemoveAll(void)
0x18000c791  mov     [rbx+140h], rbp
0x18000c798  mov     [rbx+15Ch], ebp
0x18000c79e  xor     eax, eax
0x18000c7a0  add     rsp, 28h
0x18000c7a4  pop     rdi
0x18000c7a5  pop     rsi
0x18000c7a6  pop     rbp
0x18000c7a7  pop     rbx
0x18000c7a8  retn
```
