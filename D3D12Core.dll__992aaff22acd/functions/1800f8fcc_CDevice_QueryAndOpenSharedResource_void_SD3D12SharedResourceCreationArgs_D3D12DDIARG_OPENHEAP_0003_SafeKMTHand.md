# CDevice::QueryAndOpenSharedResource(void *,SD3D12SharedResourceCreationArgs &,D3D12DDIARG_OPENHEAP_0003 &,SafeKMTHandle &,SafeKMTHandle &,SafeKMTHandle &,bool,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &)

- ea: `0x1800f8fcc`
- end: `0x1800f94fa`
- name: `?QueryAndOpenSharedResource@CDevice@@QEAAXPEAXAEAUSD3D12SharedResourceCreationArgs@@AEAUD3D12DDIARG_OPENHEAP_0003@@AEAVSafeKMTHandle@@33_NAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@55@Z`
- size: `1326`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005148c`

## callees

- `0x180007df0`
- `0x18000b010`
- `0x18000b920`
- `0x18000bfd8`
- `0x18004822c`
- `0x18004858c`
- `0x1800488f8`
- `0x18004ed34`
- `0x1800528ac`
- `0x1800bb480`
- `0x1800bc07c`
- `0x1800bc094`
- `0x1800ccd34`
- `0x1800ccd84`
- `0x1800e6fac`
- `0x1800f8fcc`
- `0x18017ad40`

## import_xrefs

- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTOpenSynchronizationObject` at `0x1800f949c`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTOpenKeyedMutex2` at `0x1800f944a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDevice::QueryAndOpenSharedResource(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        SafeKMTHandle *a6,
        SafeKMTHandle *a7,
        bool a8,
        __int64 a9,
        _QWORD *a10,
        _QWORD *a11)
{
  __int64 v11; // r12
  SafeKMTHandle *v14; // r13
  _OWORD *v15; // rsi
  unsigned int ResourceInfo; // eax
  int v17; // eax
  int v18; // eax
  unsigned __int64 v19; // r15
  unsigned int *v20; // r14
  void *v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rdi
  _DWORD *v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r12
  size_t v27; // rbx
  size_t v28; // r8
  unsigned int *v29; // r9
  int v30; // eax
  __int64 v31; // rbx
  unsigned __int64 v32; // r15
  bool i; // zf
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rax
  unsigned int v37; // eax
  int v38; // eax
  int v39; // ebx
  __int64 v40; // rdx
  __int64 v41; // r8
  unsigned int v42; // eax
  int v43; // eax
  int v44; // ebx
  SafeKMTHandle *v45; // rdi
  SIZE_T v47; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v48; // [rsp+68h] [rbp-98h]
  unsigned __int64 v49; // [rsp+70h] [rbp-90h]
  __int64 v50; // [rsp+78h] [rbp-88h]
  _DWORD *v51; // [rsp+80h] [rbp-80h]
  _QWORD *v52; // [rsp+88h] [rbp-78h]
  SafeKMTHandle *v53; // [rsp+90h] [rbp-70h]
  __int128 v54; // [rsp+98h] [rbp-68h] BYREF
  SIZE_T dwBytes[2]; // [rsp+A8h] [rbp-58h]
  __int64 v56; // [rsp+B8h] [rbp-48h]
  __int64 v57; // [rsp+C0h] [rbp-40h]
  SafeKMTHandle *v58; // [rsp+C8h] [rbp-38h]
  unsigned int *v59; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v60; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v61; // [rsp+E8h] [rbp-18h]
  __int128 v62; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v63[5]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v64; // [rsp+150h] [rbp+50h]

  v11 = a4;
  v57 = a4;
  v56 = a3;
  v50 = a1;
  v51 = a5;
  v14 = a6;
  v58 = a6;
  v53 = a7;
  v52 = a10;
  v48 = a11;
  v15 = (_OWORD *)(a3 + 24);
  v54 = 0;
  *(_OWORD *)dwBytes = 0;
  ResourceInfo = NDXGI::CDevice::QueryResourceInfo(
                   *(NDXGI::CDevice **)(a1 + 760),
                   a8,
                   a2,
                   (struct NONSXS_QUERYRESOURCEINFO *)&v54,
                   0);
  v17 = NDXGI::CDevice::NTStatusToHResult(*(_QWORD *)(a1 + 760), ResourceInfo, 1);
  ThrowFailure(v17);
  v47 = (SIZE_T)operator new(HIDWORD(dwBytes[0]));
  std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(a9, &v47);
  Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(&v47);
  v47 = (SIZE_T)operator new(LODWORD(dwBytes[1]));
  std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(a10, &v47);
  Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(&v47);
  v47 = 0;
  v18 = ULongLongMult(0x50u, HIDWORD(dwBytes[1]), &v47);
  ThrowFailure(v18);
  v47 = (SIZE_T)operator new(v47);
  std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(v48, &v47);
  Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(&v47);
  v19 = LODWORD(dwBytes[0]);
  v49 = LODWORD(dwBytes[0]);
  v20 = (unsigned int *)operator new(LODWORD(dwBytes[0]));
  v59 = v20;
  v21 = a2;
  LOBYTE(v22) = a8;
  v23 = v50;
  CDevice::OpenSharedResource(v50, v22, v21, &v54, v20, a9, v52, v48, v51, a6, v53);
  memset_0(v15, 0, 0x118u);
  if ( v19 >= 8 )
  {
    v26 = v56;
    do
    {
      LODWORD(v27) = *v20;
      if ( v20[1] == 4 && (unsigned int)v27 >= 0x68 )
      {
        *v15 = *(_OWORD *)v20;
        v15[1] = *((_OWORD *)v20 + 1);
        v15[2] = *((_OWORD *)v20 + 2);
        v15[3] = *((_OWORD *)v20 + 3);
        v15[4] = *((_OWORD *)v20 + 4);
        v15[5] = *((_OWORD *)v20 + 5);
        *((_QWORD *)v15 + 12) = *((_QWORD *)v20 + 12);
        *(_DWORD *)v15 = 104;
      }
      else if ( v20[1] == 6 && (v27 = *v20, (unsigned int)v27 >= 0xC) )
      {
        if ( v20[2] || (unsigned int)v27 < 0x48 )
        {
          *(_QWORD *)&v62 = 0x600000068LL;
          *((_QWORD *)&v62 + 1) = 1;
          HIDWORD(v64) = 0;
          memset_0(v63, 0, 0x58u);
          v28 = v27;
          if ( (unsigned int)v27 >= 0x68 )
            v28 = 104;
          memcpy_0(&v62, v20, v28);
          v15[11] = v62;
          v15[12] = v63[0];
          v15[13] = v63[1];
          v15[14] = v63[2];
          v15[15] = v63[3];
          v15[16] = v63[4];
          *((_QWORD *)v15 + 34) = v64;
          *((_DWORD *)v15 + 44) = 104;
          v60 = 0;
          v61 = 0;
          v30 = ParseSharedResourceExtensions(
                  (const unsigned __int8 *)v20,
                  *v20,
                  (struct D3D12_SHARED_RESOURCE_EXT_PARSED *)&v60,
                  v29);
          ThrowFailure(v30);
          v31 = 0;
          do
          {
            v32 = *((_QWORD *)&v60 + v31);
            LODWORD(v47) = 0;
            for ( i = !_BitScanForward64((unsigned __int64 *)&v34, v32);
                  !i;
                  i = !_BitScanForward64((unsigned __int64 *)&v34, v32) )
            {
              v35 = ((_DWORD)v31 << 6) + v34;
              LODWORD(v47) = v35;
              v24 = *(_DWORD **)(v26 + 360);
              if ( v24 == *(_DWORD **)(v26 + 368) )
              {
                std::vector<enum DXGI_FORMAT>::_Emplace_reallocate<enum DXGI_FORMAT>(v26 + 352, v24, &v47);
              }
              else
              {
                *v24 = v35;
                *(_QWORD *)(v26 + 360) += 4LL;
              }
              v32 &= v32 - 1;
            }
            v31 = (unsigned int)(v31 + 1);
          }
          while ( (unsigned int)v31 < 3 );
          v19 = v49;
        }
        else
        {
          *(_OWORD *)((char *)v15 + 104) = *(_OWORD *)v20;
          *(_OWORD *)((char *)v15 + 120) = *((_OWORD *)v20 + 1);
          *(_OWORD *)((char *)v15 + 136) = *((_OWORD *)v20 + 2);
          *(_OWORD *)((char *)v15 + 152) = *((_OWORD *)v20 + 3);
          *((_QWORD *)v15 + 21) = *((_QWORD *)v20 + 8);
          *((_DWORD *)v15 + 26) = 72;
        }
      }
      else if ( (unsigned int)v27 >= 0x38 )
      {
        *v15 = *(_OWORD *)v20;
        v15[1] = *((_OWORD *)v20 + 1);
        v15[2] = *((_OWORD *)v20 + 2);
        *((_QWORD *)v15 + 6) = *((_QWORD *)v20 + 6);
        *(_QWORD *)v15 = 56;
      }
      v36 = *v20;
      v19 -= v36;
      v49 = v19;
      v20 = (unsigned int *)((char *)v20 + v36);
    }
    while ( v19 >= 8 );
    v11 = v57;
    v14 = v58;
    v23 = v50;
  }
  *(_DWORD *)v11 = HIDWORD(dwBytes[1]);
  *(_QWORD *)(v11 + 8) = *v48;
  *(_DWORD *)(v11 + 16) = *v51;
  *(_QWORD *)(v11 + 24) = *v52;
  *(_DWORD *)(v11 + 32) = dwBytes[1];
  if ( !*(_DWORD *)v14 && *((_DWORD *)v15 + 7) )
  {
    DWORD1(v60) = 0;
    v61 = 4;
    LODWORD(v47) = 0;
    *((_QWORD *)&v60 + 1) = &v47;
    LODWORD(v60) = *((_DWORD *)v15 + 8);
    v37 = CallAndLogImpl<long (*)(_D3DKMT_OPENKEYEDMUTEX2 *),_D3DKMT_OPENKEYEDMUTEX2 *>(
            D3DKMTOpenKeyedMutex2,
            v24,
            v25,
            &v60);
    v38 = NDXGI::CDevice::NTStatusToHResult(*(_QWORD *)(v23 + 760), v37, 1);
    ThrowFailure(v38);
    v39 = DWORD1(v60);
    SafeKMTHandle::Release(v14);
    *(_DWORD *)v14 = v39;
    memset_0(&v62, 0, 0x48u);
    LODWORD(v62) = *((_DWORD *)v15 + 9);
    v42 = CallAndLogImpl<long (*)(_D3DKMT_OPENSYNCHRONIZATIONOBJECT *),_D3DKMT_OPENSYNCHRONIZATIONOBJECT *>(
            D3DKMTOpenSynchronizationObject,
            v40,
            v41,
            &v62);
    v43 = NDXGI::CDevice::NTStatusToHResult(*(_QWORD *)(v23 + 760), v42, 1);
    ThrowFailure(v43);
    v44 = DWORD1(v62);
    v45 = v53;
    SafeKMTHandle::Release(v53);
    *(_DWORD *)v45 = v44;
  }
  return Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(&v59);
}

```

## disassembly

```asm
0x1800f8fcc  push    rbp
0x1800f8fce  push    rbx
0x1800f8fcf  push    rsi
0x1800f8fd0  push    rdi
0x1800f8fd1  push    r12
0x1800f8fd3  push    r13
0x1800f8fd5  push    r14
0x1800f8fd7  push    r15
0x1800f8fd9  lea     rbp, [rsp-78h]
0x1800f8fde  sub     rsp, 178h
0x1800f8fe5  mov     rax, cs:__security_cookie
0x1800f8fec  xor     rax, rsp
0x1800f8fef  mov     [rbp+0B0h+var_50], rax
0x1800f8ff3  mov     r12, r9
0x1800f8ff6  mov     [rbp+0B0h+var_F0], r9
0x1800f8ffa  mov     [rbp+0B0h+var_F8], r8
0x1800f8ffe  mov     rdi, rdx
0x1800f9001  mov     r14, rcx
0x1800f9004  mov     [rsp+1B0h+var_138], rcx
0x1800f9009  mov     rax, [rbp+0B0h+arg_20]
0x1800f9010  mov     [rbp+0B0h+var_130], rax
0x1800f9014  mov     r13, [rbp+0B0h+arg_28]
0x1800f901b  mov     [rbp+0B0h+var_E8], r13
0x1800f901f  mov     rax, [rbp+0B0h+arg_30]
0x1800f9026  mov     [rbp+0B0h+var_120], rax
0x1800f902a  mov     rbx, [rbp+0B0h+arg_40]
0x1800f9031  mov     r15, [rbp+0B0h+arg_48]
0x1800f9038  mov     [rbp+0B0h+var_128], r15
0x1800f903c  mov     rax, [rbp+0B0h+arg_50]
0x1800f9043  mov     [rsp+1B0h+var_148], rax
0x1800f9048  lea     rsi, [r8+18h]
0x1800f904c  xorps   xmm0, xmm0
0x1800f904f  movups  [rbp+0B0h+var_118], xmm0
0x1800f9053  movups  xmmword ptr [rbp+0B0h+dwBytes], xmm0
0x1800f9057  mov     [rsp+1B0h+var_190], 0; bool
0x1800f905c  lea     r9, [rbp+0B0h+var_118]; struct NONSXS_QUERYRESOURCEINFO *
0x1800f9060  mov     r8, rdx; void *
0x1800f9063  mov     dl, [rbp+0B0h+arg_38]; bool
0x1800f9069  mov     rcx, [rcx+2F8h]; this
0x1800f9070  call    ?QueryResourceInfo@CDevice@NDXGI@@QEAAJ_NPEAXPEAUNONSXS_QUERYRESOURCEINFO@@0@Z; NDXGI::CDevice::QueryResourceInfo(bool,void *,NONSXS_QUERYRESOURCEINFO *,bool)
0x1800f9075  mov     r8d, 1
0x1800f907b  mov     edx, eax
0x1800f907d  mov     rcx, [r14+2F8h]
0x1800f9084  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CDevice::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x1800f9089  mov     ecx, eax; int
0x1800f908b  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f9090  mov     ecx, dword ptr [rbp+0B0h+dwBytes+4]; dwBytes
0x1800f9093  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f9098  mov     [rsp+1B0h+var_150], rax
0x1800f909d  lea     rdx, [rsp+1B0h+var_150]
0x1800f90a2  mov     rcx, rbx
0x1800f90a5  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x1800f90aa  lea     rcx, [rsp+1B0h+var_150]
0x1800f90af  call    ??1?$MakeAllocator@UCD3DShaderCacheInstallerFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(void)
0x1800f90b4  mov     ecx, dword ptr [rbp+0B0h+dwBytes+8]; dwBytes
0x1800f90b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f90bc  mov     [rsp+1B0h+var_150], rax
0x1800f90c1  lea     rdx, [rsp+1B0h+var_150]
0x1800f90c6  mov     rcx, r15
0x1800f90c9  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x1800f90ce  lea     rcx, [rsp+1B0h+var_150]
0x1800f90d3  call    ??1?$MakeAllocator@UCD3DShaderCacheInstallerFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(void)
0x1800f90d8  mov     [rsp+1B0h+var_150], 0
0x1800f90e1  mov     edx, dword ptr [rbp+0B0h+dwBytes+0Ch]; unsigned __int64
0x1800f90e4  lea     r8, [rsp+1B0h+var_150]; unsigned __int64 *
0x1800f90e9  mov     ecx, 50h ; 'P'; unsigned __int64
0x1800f90ee  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800f90f3  mov     ecx, eax; int
0x1800f90f5  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f90fa  mov     rcx, [rsp+1B0h+var_150]; dwBytes
0x1800f90ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f9104  mov     [rsp+1B0h+var_150], rax
0x1800f9109  lea     rdx, [rsp+1B0h+var_150]
0x1800f910e  mov     rcx, [rsp+1B0h+var_148]
0x1800f9113  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x1800f9118  lea     rcx, [rsp+1B0h+var_150]
0x1800f911d  call    ??1?$MakeAllocator@UCD3DShaderCacheInstallerFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(void)
0x1800f9122  mov     r15d, dword ptr [rbp+0B0h+dwBytes]
0x1800f9126  mov     [rsp+1B0h+var_140], r15
0x1800f912b  mov     ecx, r15d; dwBytes
0x1800f912e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f9133  mov     r14, rax
0x1800f9136  mov     [rbp+0B0h+var_E0], rax
0x1800f913a  mov     rax, [rbp+0B0h+var_120]
0x1800f913e  mov     [rsp+1B0h+var_160], rax
0x1800f9143  mov     [rsp+1B0h+var_168], r13
0x1800f9148  mov     rax, [rbp+0B0h+var_130]
0x1800f914c  mov     [rsp+1B0h+var_170], rax
0x1800f9151  mov     rax, [rsp+1B0h+var_148]
0x1800f9156  mov     [rsp+1B0h+var_178], rax
0x1800f915b  mov     rax, [rbp+0B0h+var_128]
0x1800f915f  mov     [rsp+1B0h+var_180], rax
0x1800f9164  mov     [rsp+1B0h+var_188], rbx
0x1800f9169  mov     qword ptr [rsp+1B0h+var_190], r14
0x1800f916e  lea     r9, [rbp+0B0h+var_118]
0x1800f9172  mov     r8, rdi
0x1800f9175  mov     dl, [rbp+0B0h+arg_38]
0x1800f917b  mov     rdi, [rsp+1B0h+var_138]
0x1800f9180  mov     rcx, rdi
0x1800f9183  call    ?OpenSharedResource@CDevice@@QEAAX_NPEAXAEBUNONSXS_QUERYRESOURCEINFO@@1AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@33AEAVSafeKMTHandle@@44@Z; CDevice::OpenSharedResource(bool,void *,NONSXS_QUERYRESOURCEINFO const &,void *,std::unique_ptr<uchar [0]> &,std::unique_ptr<uchar [0]> &,std::unique_ptr<uchar [0]> &,SafeKMTHandle &,SafeKMTHandle &,SafeKMTHandle &)
0x1800f9188  xor     edx, edx; Val
0x1800f918a  mov     r8d, 118h; Size
0x1800f9190  mov     rcx, rsi; void *
0x1800f9193  call    memset_0
0x1800f9198  cmp     r15, 8
0x1800f919c  jb      loc_1800F93E0
0x1800f91a2  mov     r12, [rbp+0B0h+var_F8]
0x1800f91a6  mov     ebx, [r14]
0x1800f91a9  cmp     dword ptr [r14+4], 4
0x1800f91ae  jnz     short loc_1800F91FF
0x1800f91b0  cmp     ebx, 68h ; 'h'
0x1800f91b3  jb      short loc_1800F91FF
0x1800f91b5  movups  xmm0, xmmword ptr [r14]
0x1800f91b9  movups  xmmword ptr [rsi], xmm0
0x1800f91bc  movups  xmm1, xmmword ptr [r14+10h]
0x1800f91c1  movups  xmmword ptr [rsi+10h], xmm1
0x1800f91c5  movups  xmm0, xmmword ptr [r14+20h]
0x1800f91ca  movups  xmmword ptr [rsi+20h], xmm0
0x1800f91ce  movups  xmm1, xmmword ptr [r14+30h]
0x1800f91d3  movups  xmmword ptr [rsi+30h], xmm1
0x1800f91d7  movups  xmm0, xmmword ptr [r14+40h]
0x1800f91dc  movups  xmmword ptr [rsi+40h], xmm0
0x1800f91e0  movups  xmm1, xmmword ptr [r14+50h]
0x1800f91e5  movups  xmmword ptr [rsi+50h], xmm1
0x1800f91e9  movsd   xmm0, qword ptr [r14+60h]
0x1800f91ef  movsd   qword ptr [rsi+60h], xmm0
0x1800f91f4  mov     dword ptr [rsi], 68h ; 'h'
0x1800f91fa  jmp     loc_1800F93BB
0x1800f91ff  cmp     dword ptr [r14+4], 6
0x1800f9204  jnz     loc_1800F938B
0x1800f920a  mov     ebx, [r14]
0x1800f920d  cmp     ebx, 0Ch
0x1800f9210  jb      loc_1800F938B
0x1800f9216  cmp     dword ptr [r14+8], 0
0x1800f921b  jnz     short loc_1800F9265
0x1800f921d  cmp     ebx, 48h ; 'H'
0x1800f9220  jb      short loc_1800F9265
0x1800f9222  movups  xmm0, xmmword ptr [r14]
0x1800f9226  movups  xmmword ptr [rsi+68h], xmm0
0x1800f922a  movups  xmm1, xmmword ptr [r14+10h]
0x1800f922f  movups  xmmword ptr [rsi+78h], xmm1
0x1800f9233  movups  xmm0, xmmword ptr [r14+20h]
0x1800f9238  movups  xmmword ptr [rsi+88h], xmm0
0x1800f923f  movups  xmm1, xmmword ptr [r14+30h]
0x1800f9244  movups  xmmword ptr [rsi+98h], xmm1
0x1800f924b  movsd   xmm0, qword ptr [r14+40h]
0x1800f9251  movsd   qword ptr [rsi+0A8h], xmm0
0x1800f9259  mov     dword ptr [rsi+68h], 48h ; 'H'
0x1800f9260  jmp     loc_1800F93BB
0x1800f9265  mov     dword ptr [rbp+0B0h+var_C0], 68h ; 'h'
0x1800f926c  mov     dword ptr [rbp+0B0h+var_C0+4], 6
0x1800f9273  mov     qword ptr [rbp+0B0h+var_C0+8], 1
0x1800f927b  xor     eax, eax
0x1800f927d  mov     [rbp+0B0h+var_5C], eax
0x1800f9280  xor     edx, edx; Val
0x1800f9282  lea     r8d, [rax+58h]; Size
0x1800f9286  lea     rcx, [rbp+0B0h+var_B0]; void *
0x1800f928a  call    memset_0
0x1800f928f  cmp     ebx, 68h ; 'h'
0x1800f9292  mov     r8, rbx
0x1800f9295  jb      short loc_1800F929D
0x1800f9297  mov     r8d, 68h ; 'h'; Size
0x1800f929d  mov     rdx, r14; Src
0x1800f92a0  lea     rcx, [rbp+0B0h+var_C0]; void *
0x1800f92a4  call    memcpy_0
0x1800f92a9  movups  xmm0, [rbp+0B0h+var_C0]
0x1800f92ad  movups  xmmword ptr [rsi+0B0h], xmm0
0x1800f92b4  movups  xmm1, [rbp+0B0h+var_B0]
0x1800f92b8  movups  xmmword ptr [rsi+0C0h], xmm1
0x1800f92bf  movups  xmm0, [rbp+0B0h+var_A0]
0x1800f92c3  movups  xmmword ptr [rsi+0D0h], xmm0
0x1800f92ca  movups  xmm1, [rbp+0B0h+var_90]
0x1800f92ce  movups  xmmword ptr [rsi+0E0h], xmm1
0x1800f92d5  movups  xmm0, [rbp+0B0h+var_80]
0x1800f92d9  movups  xmmword ptr [rsi+0F0h], xmm0
0x1800f92e0  movups  xmm1, [rbp+0B0h+var_70]
0x1800f92e4  movups  xmmword ptr [rsi+100h], xmm1
0x1800f92eb  movsd   xmm0, qword ptr [rbp+50h]
0x1800f92f0  movsd   qword ptr [rsi+110h], xmm0
0x1800f92f8  mov     dword ptr [rsi+0B0h], 68h ; 'h'
0x1800f9302  xorps   xmm1, xmm1
0x1800f9305  xor     eax, eax
0x1800f9307  movups  [rbp+0B0h+var_D8], xmm1
0x1800f930b  mov     [rbp+0B0h+var_C8], rax
0x1800f930f  lea     r8, [rbp+0B0h+var_D8]; struct D3D12_SHARED_RESOURCE_EXT_PARSED *
0x1800f9313  mov     edx, [r14]; unsigned int
0x1800f9316  mov     rcx, r14; unsigned __int8 *
0x1800f9319  call    ?ParseSharedResourceExtensions@@YAJPEBEIAEAUD3D12_SHARED_RESOURCE_EXT_PARSED@@PEAI@Z; ParseSharedResourceExtensions(uchar const *,uint,D3D12_SHARED_RESOURCE_EXT_PARSED &,uint *)
0x1800f931e  mov     ecx, eax; int
0x1800f9320  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f9325  xor     ebx, ebx
0x1800f9327  mov     r15, qword ptr [rbp+rbx*8+0B0h+var_D8]
0x1800f932c  mov     dword ptr [rsp+1B0h+var_150], 0
0x1800f9334  bsf     rax, r15
0x1800f9338  jz      short loc_1800F937D
0x1800f933a  lea     rdi, [r12+160h]
0x1800f9342  mov     r13d, ebx
0x1800f9345  shl     r13d, 6
0x1800f9349  add     eax, r13d
0x1800f934c  mov     dword ptr [rsp+1B0h+var_150], eax
0x1800f9350  mov     rdx, [rdi+8]
0x1800f9354  cmp     rdx, [rdi+10h]
0x1800f9358  jz      short loc_1800F9363
0x1800f935a  mov     [rdx], eax
0x1800f935c  add     qword ptr [rdi+8], 4
0x1800f9361  jmp     short loc_1800F9370
0x1800f9363  lea     r8, [rsp+1B0h+var_150]
0x1800f9368  mov     rcx, rdi
0x1800f936b  call    ??$_Emplace_reallocate@W4DXGI_FORMAT@@@?$vector@W4DXGI_FORMAT@@V?$allocator@W4DXGI_FORMAT@@@std@@@std@@AEAAPEAW4DXGI_FORMAT@@QEAW42@$$QEAW42@@Z; std::vector<DXGI_FORMAT>::_Emplace_reallocate<DXGI_FORMAT>(DXGI_FORMAT * const,DXGI_FORMAT &&)
0x1800f9370  lea     rax, [r15-1]
0x1800f9374  and     r15, rax
0x1800f9377  bsf     rax, r15
0x1800f937b  jnz     short loc_1800F9349
0x1800f937d  inc     ebx
0x1800f937f  cmp     ebx, 3
0x1800f9382  jb      short loc_1800F9327
0x1800f9384  mov     r15, [rsp+1B0h+var_140]
0x1800f9389  jmp     short loc_1800F93BB
0x1800f938b  cmp     ebx, 38h ; '8'
0x1800f938e  jb      short loc_1800F93BB
0x1800f9390  movups  xmm0, xmmword ptr [r14]
0x1800f9394  movups  xmmword ptr [rsi], xmm0
0x1800f9397  movups  xmm1, xmmword ptr [r14+10h]
0x1800f939c  movups  xmmword ptr [rsi+10h], xmm1
0x1800f93a0  movups  xmm0, xmmword ptr [r14+20h]
0x1800f93a5  movups  xmmword ptr [rsi+20h], xmm0
0x1800f93a9  movsd   xmm1, qword ptr [r14+30h]
0x1800f93af  movsd   qword ptr [rsi+30h], xmm1
0x1800f93b4  mov     qword ptr [rsi], 38h ; '8'
0x1800f93bb  mov     eax, [r14]
0x1800f93be  sub     r15, rax
0x1800f93c1  mov     [rsp+1B0h+var_140], r15
0x1800f93c6  add     r14, rax
0x1800f93c9  cmp     r15, 8
0x1800f93cd  jnb     loc_1800F91A6
0x1800f93d3  mov     r12, [rbp+0B0h+var_F0]
0x1800f93d7  mov     r13, [rbp+0B0h+var_E8]
0x1800f93db  mov     rdi, [rsp+1B0h+var_138]
0x1800f93e0  mov     eax, dword ptr [rbp+0B0h+dwBytes+0Ch]
0x1800f93e3  mov     [r12], eax
0x1800f93e7  mov     rax, [rsp+1B0h+var_148]
0x1800f93ec  mov     rax, [rax]
0x1800f93ef  mov     [r12+8], rax
0x1800f93f4  mov     rax, [rbp+0B0h+var_130]
0x1800f93f8  mov     eax, [rax]
0x1800f93fa  mov     [r12+10h], eax
0x1800f93ff  mov     rax, [rbp+0B0h+var_128]
0x1800f9403  mov     rax, [rax]
0x1800f9406  mov     [r12+18h], rax
0x1800f940b  mov     eax, dword ptr [rbp+0B0h+dwBytes+8]
0x1800f940e  mov     [r12+20h], eax
0x1800f9413  xor     eax, eax
0x1800f9415  cmp     [r13+0], eax
0x1800f9419  jnz     loc_1800F94D1
0x1800f941f  cmp     [rsi+1Ch], eax
0x1800f9422  jz      loc_1800F94D1
0x1800f9428  mov     dword ptr [rbp+0B0h+var_D8+4], eax
0x1800f942b  mov     [rbp+0B0h+var_C8], 4
0x1800f9433  mov     dword ptr [rsp+1B0h+var_150], eax
0x1800f9437  lea     rax, [rsp+1B0h+var_150]
0x1800f943c  mov     qword ptr [rbp+0B0h+var_D8+8], rax
0x1800f9440  mov     eax, [rsi+20h]
0x1800f9443  mov     dword ptr [rbp+0B0h+var_D8], eax
0x1800f9446  lea     r9, [rbp+0B0h+var_D8]
0x1800f944a  mov     rcx, cs:__imp_D3DKMTOpenKeyedMutex2
0x1800f9451  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_OPENKEYEDMUTEX2@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_OPENKEYEDMUTEX2@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(_D3DKMT_OPENKEYEDMUTEX2 *),_D3DKMT_OPENKEYEDMUTEX2 *>(long (*)(_D3DKMT_OPENKEYEDMUTEX2 *),char const *,RecordStatusFilterResult (*)(long),_D3DKMT_OPENKEYEDMUTEX2 *)
0x1800f9456  mov     r14d, 1
0x1800f945c  mov     r8d, r14d
0x1800f945f  mov     edx, eax
0x1800f9461  mov     rcx, [rdi+2F8h]
0x1800f9468  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CDevice::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x1800f946d  mov     ecx, eax; int
0x1800f946f  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f9474  mov     ebx, dword ptr [rbp+0B0h+var_D8+4]
0x1800f9477  mov     rcx, r13; this
0x1800f947a  call    ?Release@SafeKMTHandle@@QEAAXXZ; SafeKMTHandle::Release(void)
0x1800f947f  mov     [r13+0], ebx
0x1800f9483  xor     edx, edx; Val
0x1800f9485  lea     r8d, [r14+47h]; Size
0x1800f9489  lea     rcx, [rbp+0B0h+var_C0]; void *
0x1800f948d  call    memset_0
0x1800f9492  mov     eax, [rsi+24h]
0x1800f9495  mov     dword ptr [rbp+0B0h+var_C0], eax
0x1800f9498  lea     r9, [rbp+0B0h+var_C0]
0x1800f949c  mov     rcx, cs:__imp_D3DKMTOpenSynchronizationObject
0x1800f94a3  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_OPENSYNCHRONIZATIONOBJECT@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_OPENSYNCHRONIZATIONOBJECT@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(_D3DKMT_OPENSYNCHRONIZATIONOBJECT *),_D3DKMT_OPENSYNCHRONIZATIONOBJECT *>(long (*)(_D3DKMT_OPENSYNCHRONIZATIONOBJECT *),char const *,RecordStatusFilterResult (*)(long),_D3DKMT_OPENSYNCHRONIZATIONOBJECT *)
0x1800f94a8  mov     r8d, r14d
0x1800f94ab  mov     edx, eax
0x1800f94ad  mov     rcx, [rdi+2F8h]
0x1800f94b4  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CDevice::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x1800f94b9  mov     ecx, eax; int
0x1800f94bb  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f94c0  mov     ebx, dword ptr [rbp+0B0h+var_C0+4]
0x1800f94c3  mov     rdi, [rbp+0B0h+var_120]
0x1800f94c7  mov     rcx, rdi; this
0x1800f94ca  call    ?Release@SafeKMTHandle@@QEAAXXZ; SafeKMTHandle::Release(void)
0x1800f94cf  mov     [rdi], ebx
0x1800f94d1  lea     rcx, [rbp+0B0h+var_E0]
0x1800f94d5  call    ??1?$MakeAllocator@UCD3DShaderCacheInstallerFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(void)
0x1800f94da  mov     rcx, [rbp+0B0h+var_50]
  ... truncated ...
```
