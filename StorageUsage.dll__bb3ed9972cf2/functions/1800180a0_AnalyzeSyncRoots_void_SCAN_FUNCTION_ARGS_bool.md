# AnalyzeSyncRoots(void *,SCAN_FUNCTION_ARGS,bool &)

- ea: `0x1800180a0`
- end: `0x1800184a3`
- name: `?AnalyzeSyncRoots@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z`
- size: `1027`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x18000a780`
- `0x180013ae4`
- `0x180016e60`
- `0x180017ac8`
- `0x180017bf8`
- `0x1800180a0`
- `0x1800195b4`
- `0x18001a2c8`
- `0x18001a368`
- `0x18001a93c`
- `0x18001b6b4`
- `0x18001ebf4`
- `0x18002af30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018438`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018438`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018426`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018426`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018148`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018148`
- `cldapi!CfGetSyncRootInfoByPath` at `0x180018317`
- `cldapi!CfGetSyncRootInfoByPath` at `0x180018317`

## pseudocode

```c
__int64 __fastcall AnalyzeSyncRoots(__int64 a1)
{
  LPVOID v2; // rbx
  int (__fastcall *v3)(LPVOID, GUID *, __int64 *); // rdi
  __int64 v4; // rdi
  int (__fastcall *v5)(__int64, __int64 *); // rbx
  int v6; // ebx
  unsigned int v7; // esi
  int v8; // r14d
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, GUID *, __int64 *); // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, __int64, _QWORD, __int64 *); // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v17; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+54h] [rbp-ACh] BYREF
  int v19; // [rsp+58h] [rbp-A8h] BYREF
  int v20; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  __int64 v23; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h] BYREF
  void *lpMem[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v26; // [rsp+90h] [rbp-70h] BYREF
  __int64 v27; // [rsp+98h] [rbp-68h]
  __int64 v28; // [rsp+A0h] [rbp-60h]
  int v29; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v30[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v31[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v32; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v33; // [rsp+D8h] [rbp-28h]
  __int64 v34; // [rsp+E0h] [rbp-20h]
  _BYTE v35[8]; // [rsp+F0h] [rbp-10h] BYREF
  int v36; // [rsp+F8h] [rbp-8h]
  int v37; // [rsp+FCh] [rbp-4h]
  unsigned __int16 v38[256]; // [rsp+10Ch] [rbp+Ch] BYREF
  _BYTE v39[7652]; // [rsp+30Ch] [rbp+20Ch] BYREF

  ppv = 0;
  v24 = 0;
  v21 = 0;
  v23 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v17 = 0;
  v29 = 0;
  v18 = 0;
  v20 = 0;
  *(_OWORD *)lpMem = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
  if ( CoCreateInstance(&rclsid, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &ppv) >= 0
    && (v2 = ppv,
        v3 = **(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv,
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24),
        v3(v2, &GUID_a2ceecd8_bae5_49ed_939b_cd07bf7b02ad, &v24) >= 0)
    && (v4 = v24,
        v5 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 24LL),
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21),
        v5(v4, &v21) >= 0)
    && (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v21 + 24LL))(v21, &v17) >= 0
    && v17 )
  {
    v6 = AllocateMemory<unsigned short>(&lpMem[1]);
    if ( v6 >= 0 )
    {
      LODWORD(lpMem[0]) = 0x80000000;
      v19 = 0;
      GetMDMPolicyIsConfigured(7, &v19);
      v7 = 0;
      v8 = v19;
      while ( v7 < v17 )
      {
        std::map<unsigned long,unsigned __int64>::map<unsigned long,unsigned __int64>(v31);
        std::map<unsigned long,unsigned __int64>::map<unsigned long,unsigned __int64>(v30);
        memset_0(lpMem[1], 0, WORD1(lpMem[0]));
        v9 = v21;
        v10 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v21 + 32LL);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
        v6 = v10(v9, v7, &GUID_ca01c124_2769_4576_bf12_8a54ee671a86, &v23);
        if ( v6 < 0 )
          goto LABEL_15;
        v11 = v23;
        v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 24LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v26);
        v27 = -1;
        v28 = -1;
        v6 = v12(v11, &v26);
        if ( v6 < 0
          || (v13 = ppv,
              v14 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64 *))(*(_QWORD *)ppv + 136LL),
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v32),
              v33 = -1,
              v34 = -1,
              v6 = v14(v13, v26, 0, &v32),
              v6 < 0) )
        {
LABEL_15:
          std::_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>(v30);
          std::_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>(v31);
          break;
        }
        if ( (int)CfGetSyncRootInfoByPath(v32, 1, v35, 0x2000, &v29) >= 0 )
        {
          GetStoragePolicySettings(1, v26, &v18);
          GetStoragePolicySettings(7, v26, &v20);
          v6 = ScanProviderSyncRoot(v32, (unsigned int)v38, (unsigned int)v31, (unsigned int)v30, (__int64)lpMem, a1);
          LogSyncRootCloudProviders(v26, (__int64)v38, (__int64)v39, v36, v37, (__int64)v31, v18, v20, v8, v6);
          LogAndClearSyncRootNotCloudFileExtensions(v38, (struct _UNICODE_STRING *)lpMem);
          LogSyncRootLastAccessTime(v26, (unsigned int)v38, (unsigned int)v39, v36, v37, (__int64)v30, v18, v6);
        }
        std::_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>(v30);
        std::_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>(v31);
        ++v7;
      }
    }
  }
  else
  {
    v6 = 0;
  }
  if ( lpMem[1] )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 8u, lpMem[1]);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v32);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v26);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800180a0  push    rbp
0x1800180a2  push    rbx
0x1800180a3  push    rsi
0x1800180a4  push    rdi
0x1800180a5  push    r12
0x1800180a7  push    r13
0x1800180a9  push    r14
0x1800180ab  push    r15
0x1800180ad  lea     rbp, [rsp-2008h]
0x1800180b5  mov     eax, 2108h
0x1800180ba  call    _alloca_probe
0x1800180bf  sub     rsp, rax
0x1800180c2  mov     rax, cs:__security_cookie
0x1800180c9  xor     rax, rsp
0x1800180cc  mov     [rbp+2040h+var_50], rax
0x1800180d3  mov     r15, rcx
0x1800180d6  xor     r12d, r12d
0x1800180d9  mov     [rsp+2140h+var_20D8], r12
0x1800180de  mov     [rsp+2140h+var_20C8], r12
0x1800180e3  mov     [rsp+2140h+var_20E0], r12
0x1800180e8  mov     [rsp+2140h+var_20D0], r12
0x1800180ed  mov     [rbp+2040h+var_20B0], r12
0x1800180f1  mov     [rbp+2040h+var_20A8], r12
0x1800180f5  mov     [rbp+2040h+var_20A0], r12
0x1800180f9  mov     [rbp+2040h+var_2070], r12
0x1800180fd  mov     [rbp+2040h+var_2068], r12
0x180018101  mov     [rbp+2040h+var_2060], r12
0x180018105  mov     [rsp+2140h+var_20F0], r12d
0x18001810a  mov     [rbp+2040h+var_2098], r12d
0x18001810e  mov     [rsp+2140h+var_20EC], r12d
0x180018113  mov     [rsp+2140h+var_20E4], r12d
0x180018118  xorps   xmm0, xmm0
0x18001811b  movups  xmmword ptr [rbp+2040h+lpMem], xmm0
0x18001811f  lea     rcx, [rsp+2140h+var_20D8]
0x180018124  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180018129  lea     rax, [rsp+2140h+var_20D8]
0x18001812e  mov     [rsp+2140h+ppv], rax; ppv
0x180018133  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x18001813a  xor     edx, edx; pUnkOuter
0x18001813c  lea     r8d, [r12+1]; dwClsContext
0x180018141  lea     rcx, rclsid; rclsid
0x180018148  call    cs:__imp_CoCreateInstance
0x18001814e  test    eax, eax
0x180018150  js      loc_18001841D
0x180018156  mov     rbx, [rsp+2140h+var_20D8]
0x18001815b  mov     rax, [rbx]
0x18001815e  mov     rdi, [rax]
0x180018161  lea     rcx, [rsp+2140h+var_20C8]
0x180018166  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001816b  lea     r8, [rsp+2140h+var_20C8]
0x180018170  lea     rdx, _GUID_a2ceecd8_bae5_49ed_939b_cd07bf7b02ad
0x180018177  mov     rcx, rbx
0x18001817a  mov     rax, rdi
0x18001817d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018182  nop
0x180018183  test    eax, eax
0x180018185  js      loc_18001841D
0x18001818b  mov     rdi, [rsp+2140h+var_20C8]
0x180018190  mov     rax, [rdi]
0x180018193  mov     rbx, [rax+18h]
0x180018197  lea     rcx, [rsp+2140h+var_20E0]
0x18001819c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800181a1  lea     rdx, [rsp+2140h+var_20E0]
0x1800181a6  mov     rcx, rdi
0x1800181a9  mov     rax, rbx
0x1800181ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181b1  test    eax, eax
0x1800181b3  js      loc_18001841D
0x1800181b9  mov     rcx, [rsp+2140h+var_20E0]
0x1800181be  mov     rax, [rcx]
0x1800181c1  lea     rdx, [rsp+2140h+var_20F0]
0x1800181c6  mov     rax, [rax+18h]
0x1800181ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181cf  test    eax, eax
0x1800181d1  js      loc_18001841D
0x1800181d7  cmp     [rsp+2140h+var_20F0], r12d
0x1800181dc  jz      loc_18001841D
0x1800181e2  lea     rcx, [rbp+2040h+lpMem+8]
0x1800181e6  call    ??$AllocateMemory@G@@YAJPEAPEAG_K@Z; AllocateMemory<ushort>(ushort * *,unsigned __int64)
0x1800181eb  mov     ebx, eax
0x1800181ed  test    eax, eax
0x1800181ef  js      loc_180018420
0x1800181f5  mov     dword ptr [rbp+2040h+lpMem], 80000000h
0x1800181fc  mov     [rsp+2140h+var_20E8], r12d
0x180018201  lea     rdx, [rsp+2140h+var_20E8]
0x180018206  lea     ecx, [r12+7]
0x18001820b  call    ?GetMDMPolicyIsConfigured@@YAJW4_STORAGE_POLICY@@PEAK@Z; GetMDMPolicyIsConfigured(_STORAGE_POLICY,ulong *)
0x180018210  mov     esi, r12d
0x180018213  or      r13, 0FFFFFFFFFFFFFFFFh
0x180018217  mov     r14d, [rsp+2140h+var_20E8]
0x18001821c  cmp     esi, [rsp+2140h+var_20F0]
0x180018220  jnb     loc_180018420
0x180018226  lea     rcx, [rbp+2040h+var_2080]
0x18001822a  call    ??0?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAA@XZ; std::map<ulong,unsigned __int64>::map<ulong,unsigned __int64>(void)
0x18001822f  nop
0x180018230  lea     rcx, [rbp+2040h+var_2090]
0x180018234  call    ??0?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAA@XZ; std::map<ulong,unsigned __int64>::map<ulong,unsigned __int64>(void)
0x180018239  nop
0x18001823a  movzx   r8d, word ptr [rbp+2040h+lpMem+2]; Size
0x18001823f  xor     edx, edx; Val
0x180018241  mov     rcx, [rbp+2040h+lpMem+8]; void *
0x180018245  call    memset_0
0x18001824a  mov     rdi, [rsp+2140h+var_20E0]
0x18001824f  mov     rax, [rdi]
0x180018252  mov     rbx, [rax+20h]
0x180018256  lea     rcx, [rsp+2140h+var_20D0]
0x18001825b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180018260  lea     r9, [rsp+2140h+var_20D0]
0x180018265  lea     r8, _GUID_ca01c124_2769_4576_bf12_8a54ee671a86
0x18001826c  mov     edx, esi
0x18001826e  mov     rcx, rdi
0x180018271  mov     rax, rbx
0x180018274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018279  mov     ebx, eax
0x18001827b  test    eax, eax
0x18001827d  js      loc_180018408
0x180018283  mov     rdi, [rsp+2140h+var_20D0]
0x180018288  mov     rax, [rdi]
0x18001828b  mov     rbx, [rax+18h]
0x18001828f  lea     rcx, [rbp+2040h+var_20B0]
0x180018293  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180018298  mov     [rbp+2040h+var_20A8], r13
0x18001829c  mov     [rbp+2040h+var_20A0], r13
0x1800182a0  lea     rdx, [rbp+2040h+var_20B0]
0x1800182a4  mov     rcx, rdi
0x1800182a7  mov     rax, rbx
0x1800182aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182af  mov     ebx, eax
0x1800182b1  test    eax, eax
0x1800182b3  js      loc_180018408
0x1800182b9  mov     rdi, [rsp+2140h+var_20D8]
0x1800182be  mov     rax, [rdi]
0x1800182c1  mov     rbx, [rax+88h]
0x1800182c8  lea     rcx, [rbp+2040h+var_2070]
0x1800182cc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800182d1  mov     [rbp+2040h+var_2068], r13
0x1800182d5  mov     [rbp+2040h+var_2060], r13
0x1800182d9  lea     r9, [rbp+2040h+var_2070]
0x1800182dd  xor     r8d, r8d
0x1800182e0  mov     rdx, [rbp+2040h+var_20B0]
0x1800182e4  mov     rcx, rdi
0x1800182e7  mov     rax, rbx
0x1800182ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182ef  mov     ebx, eax
0x1800182f1  test    eax, eax
0x1800182f3  js      loc_180018408
0x1800182f9  lea     rax, [rbp+2040h+var_2098]
0x1800182fd  mov     [rsp+2140h+ppv], rax
0x180018302  mov     r9d, 2000h
0x180018308  lea     r8, [rbp+2040h+var_2050]
0x18001830c  mov     edi, 1
0x180018311  mov     edx, edi
0x180018313  mov     rcx, [rbp+2040h+var_2070]
0x180018317  call    cs:__imp_CfGetSyncRootInfoByPath
0x18001831d  test    eax, eax
0x18001831f  js      loc_1800183EE
0x180018325  lea     r8, [rsp+2140h+var_20EC]
0x18001832a  mov     rdx, [rbp+2040h+var_20B0]
0x18001832e  mov     ecx, edi
0x180018330  call    GetStoragePolicySettings
0x180018335  lea     r8, [rsp+2140h+var_20E4]
0x18001833a  mov     rdx, [rbp+2040h+var_20B0]
0x18001833e  lea     ecx, [rdi+6]
0x180018341  call    GetStoragePolicySettings
0x180018346  mov     [rsp+2140h+var_2118], r15
0x18001834b  lea     rax, [rbp+2040h+lpMem]
0x18001834f  mov     [rsp+2140h+ppv], rax
0x180018354  lea     r9, [rbp+2040h+var_2090]
0x180018358  lea     r8, [rbp+2040h+var_2080]
0x18001835c  lea     rdx, [rbp+2040h+var_2034]
0x180018360  mov     rcx, [rbp+2040h+var_2070]
0x180018364  call    ?ScanProviderSyncRoot@@YAJPEBG0PEAV?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@1PEAU_UNICODE_STRING@@PEAX@Z; ScanProviderSyncRoot(ushort const *,ushort const *,std::map<ulong,unsigned __int64> *,std::map<ulong,unsigned __int64> *,_UNICODE_STRING *,void *)
0x180018369  mov     ebx, eax
0x18001836b  mov     eax, [rbp+2040h+var_2044]
0x18001836e  mov     [rsp+2140h+var_20F8], ebx
0x180018372  mov     [rsp+2140h+var_2100], r14d
0x180018377  mov     ecx, [rsp+2140h+var_20E4]
0x18001837b  mov     [rsp+2140h+var_2108], ecx
0x18001837f  mov     ecx, [rsp+2140h+var_20EC]
0x180018383  mov     [rsp+2140h+var_2110], ecx
0x180018387  lea     rcx, [rbp+2040h+var_2080]
0x18001838b  mov     [rsp+2140h+var_2118], rcx
0x180018390  mov     dword ptr [rsp+2140h+ppv], eax
0x180018394  mov     r9d, [rbp+2040h+var_2048]
0x180018398  lea     r8, [rbp+2040h+var_1E34]
0x18001839f  lea     rdx, [rbp+2040h+var_2034]
0x1800183a3  mov     rcx, [rbp+2040h+var_20B0]
0x1800183a7  call    ?LogSyncRootCloudProviders@@YAXPEBG00UCF_HYDRATION_POLICY@@UCF_POPULATION_POLICY@@PEAV?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@KKKJ@Z; LogSyncRootCloudProviders(ushort const *,ushort const *,ushort const *,CF_HYDRATION_POLICY,CF_POPULATION_POLICY,std::map<ulong,unsigned __int64> *,ulong,ulong,ulong,long)
0x1800183ac  lea     rdx, [rbp+2040h+lpMem]; struct _UNICODE_STRING *
0x1800183b0  lea     rcx, [rbp+2040h+var_2034]; unsigned __int16 *
0x1800183b4  call    ?LogAndClearSyncRootNotCloudFileExtensions@@YAXPEBGPEAU_UNICODE_STRING@@@Z; LogAndClearSyncRootNotCloudFileExtensions(ushort const *,_UNICODE_STRING *)
0x1800183b9  mov     eax, [rbp+2040h+var_2044]
0x1800183bc  mov     [rsp+2140h+var_2108], ebx
0x1800183c0  mov     ecx, [rsp+2140h+var_20EC]
0x1800183c4  mov     [rsp+2140h+var_2110], ecx
0x1800183c8  lea     rcx, [rbp+2040h+var_2090]
0x1800183cc  mov     [rsp+2140h+var_2118], rcx
0x1800183d1  mov     dword ptr [rsp+2140h+ppv], eax
0x1800183d5  mov     r9d, [rbp+2040h+var_2048]
0x1800183d9  lea     r8, [rbp+2040h+var_1E34]
0x1800183e0  lea     rdx, [rbp+2040h+var_2034]
0x1800183e4  mov     rcx, [rbp+2040h+var_20B0]
0x1800183e8  call    ?LogSyncRootLastAccessTime@@YAXPEBG00UCF_HYDRATION_POLICY@@UCF_POPULATION_POLICY@@PEAV?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@KJ@Z; LogSyncRootLastAccessTime(ushort const *,ushort const *,ushort const *,CF_HYDRATION_POLICY,CF_POPULATION_POLICY,std::map<ulong,unsigned __int64> *,ulong,long)
0x1800183ed  nop
0x1800183ee  lea     rcx, [rbp+2040h+var_2090]
0x1800183f2  call    ??1?$_Tree@V?$_Tmap_traits@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>(void)
0x1800183f7  nop
0x1800183f8  lea     rcx, [rbp+2040h+var_2080]
0x1800183fc  call    ??1?$_Tree@V?$_Tmap_traits@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>(void)
0x180018401  add     esi, edi
0x180018403  jmp     loc_18001821C
0x180018408  lea     rcx, [rbp+2040h+var_2090]
0x18001840c  call    ??1?$_Tree@V?$_Tmap_traits@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>(void)
0x180018411  nop
0x180018412  lea     rcx, [rbp+2040h+var_2080]
0x180018416  call    ??1?$_Tree@V?$_Tmap_traits@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>(void)
0x18001841b  jmp     short loc_180018420
0x18001841d  mov     ebx, r12d
0x180018420  cmp     [rbp+2040h+lpMem+8], r12
0x180018424  jz      short loc_18001843F
0x180018426  call    cs:__imp_GetProcessHeap
0x18001842c  mov     rcx, rax; hHeap
0x18001842f  mov     r8, [rbp+2040h+lpMem+8]; lpMem
0x180018433  mov     edx, 8; dwFlags
0x180018438  call    cs:__imp_HeapFree
0x18001843e  nop
0x18001843f  lea     rcx, [rbp+2040h+var_2070]
0x180018443  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180018448  nop
0x180018449  lea     rcx, [rbp+2040h+var_20B0]
0x18001844d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180018452  nop
0x180018453  lea     rcx, [rsp+2140h+var_20D0]
0x180018458  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001845d  nop
0x18001845e  lea     rcx, [rsp+2140h+var_20E0]
0x180018463  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180018468  nop
0x180018469  lea     rcx, [rsp+2140h+var_20C8]
0x18001846e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180018473  nop
0x180018474  lea     rcx, [rsp+2140h+var_20D8]
0x180018479  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001847e  mov     eax, ebx
0x180018480  mov     rcx, [rbp+2040h+var_50]
0x180018487  xor     rcx, rsp; StackCookie
0x18001848a  call    __security_check_cookie
0x18001848f  add     rsp, 2108h
0x180018496  pop     r15
0x180018498  pop     r14
0x18001849a  pop     r13
0x18001849c  pop     r12
0x18001849e  pop     rdi
0x18001849f  pop     rsi
0x1800184a0  pop     rbx
0x1800184a1  pop     rbp
0x1800184a2  retn
```
