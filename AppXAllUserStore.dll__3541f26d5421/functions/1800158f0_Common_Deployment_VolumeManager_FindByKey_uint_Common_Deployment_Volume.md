# Common::Deployment::VolumeManager::FindByKey(uint,Common::Deployment::Volume *)

- ea: `0x1800158f0`
- end: `0x180015b64`
- name: `?FindByKey@VolumeManager@Deployment@Common@@SAJIPEAVVolume@23@@Z`
- size: `628`
- prototype: `__int64 __fastcall(unsigned int, struct Common::Deployment::Volume *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800399a0`

## callees

- `0x180007a10`
- `0x18000d710`
- `0x1800123d8`
- `0x1800158f0`
- `0x180015b6c`
- `0x180015be8`
- `0x180015f20`
- `0x180017f50`
- `0x180018248`
- `0x18004b100`
- `0x18004c9d0`

## import_xrefs

- `ntdll!RtlLookupElementGenericTableAvl` at `0x180015948`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180015948`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180015a9b`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180015a9b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015924`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015924`

## string_xrefs

- `0x180015972`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x1800159f9`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x180015a2a`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x180015acf`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x180015af4`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x180015b15`: `onecore\admin\appmodel\common\volumemanager.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::VolumeManager::FindByKey(unsigned int a1, struct Common::Deployment::Volume *a2)
{
  PVOID v3; // rax
  Common::Deployment::Volume *v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // r8d
  unsigned int *v8; // rbx
  int v9; // eax
  int Volume; // edi
  __int64 v11; // rdx
  unsigned int v12; // edx
  Common::Deployment::Volume *v13; // rcx
  unsigned int *v14; // r14
  unsigned int v15; // edx
  unsigned int *v16; // rcx
  int NewElement; // [rsp+20h] [rbp-50h] BYREF
  unsigned int v19; // [rsp+28h] [rbp-48h] BYREF
  unsigned int *Buffer; // [rsp+30h] [rbp-40h] BYREF
  unsigned int *v21; // [rsp+38h] [rbp-38h]
  RTL_SRWLOCK *v22; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 v23[12]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v19 = a1;
  AcquireSRWLockExclusive(&SRWLock);
  v22 = &SRWLock;
  Buffer = &v19;
  v21 = 0;
  v3 = RtlLookupElementGenericTableAvl(&Common::Deployment::VolumeManager::s_volumeCache, &Buffer);
  if ( !v3 || (v4 = (Common::Deployment::Volume *)*((_QWORD *)v3 + 1)) == 0 )
  {
    Buffer = 0;
    Common::GlobalHeap::Alloc(0x70u, (void **)&Buffer);
    v8 = Buffer;
    if ( !Buffer )
    {
      Volume = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x791,
        (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
        (const char *)0x8007000ELL,
        NewElement);
      v13 = 0;
      goto LABEL_25;
    }
    *(_QWORD *)Buffer = 0;
    *((_QWORD *)v8 + 3) = 0;
    *(_OWORD *)(v8 + 2) = 0;
    *((_QWORD *)v8 + 6) = 0;
    *((_OWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 9) = 0;
    *(_OWORD *)(v8 + 14) = 0;
    *((_QWORD *)v8 + 12) = 0;
    *((_OWORD *)v8 + 5) = 0;
    *((_WORD *)v8 + 52) = 0;
    memset(v23, 0, 22);
    v9 = Common::UInt32::Encode(v19, v23, v7, (unsigned int *)&Buffer);
    Volume = v9;
    if ( v9 >= 0 )
    {
      Volume = Common::Deployment::VolumeManager::ReadVolume(v23, (struct Common::Deployment::Volume *)v8);
      if ( Volume >= 0 )
      {
        Volume = Common::Deployment::Volume::CopyTo((Common::Deployment::Volume *)v8, a2);
        if ( Volume >= 0 )
        {
          Buffer = 0;
          Common::GlobalHeap::Alloc(4u, (void **)&Buffer);
          v14 = Buffer;
          if ( Buffer )
          {
            *Buffer = v19;
            Buffer = v14;
            v21 = v8;
            LOBYTE(NewElement) = 0;
            if ( RtlInsertElementGenericTableAvl(
                   &Common::Deployment::VolumeManager::s_volumeCache,
                   &Buffer,
                   0x10u,
                   (PBOOLEAN)&NewElement) )
            {
              if ( (_BYTE)NewElement )
              {
                Common::GlobalHeap::Free(0);
                Common::DeallocateRaw<Common::Deployment::Volume *>(0, v15);
                goto LABEL_19;
              }
              Volume = -2147024198;
            }
            else
            {
              Volume = -2147024882;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x79C,
              (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
              (const char *)(unsigned int)Volume,
              NewElement);
            v16 = v14;
          }
          else
          {
            Volume = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x79B,
              (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
              (const char *)0x8007000ELL,
              NewElement);
            v16 = 0;
          }
          Common::GlobalHeap::Free(v16);
          goto LABEL_11;
        }
        v11 = 1944;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
          (const char *)(unsigned int)Volume,
          NewElement);
LABEL_11:
        v13 = (Common::Deployment::Volume *)v8;
LABEL_25:
        Common::DeallocateRaw<Common::Deployment::Volume *>(v13, v12);
        v6 = Volume;
        goto LABEL_26;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x856,
        (int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
        (const char *)(unsigned int)v9);
    }
    v11 = 1938;
    goto LABEL_10;
  }
  v5 = Common::Deployment::Volume::CopyTo(v4, a2);
  v6 = v5;
  if ( v5 >= 0 )
  {
LABEL_19:
    v6 = 0;
    goto LABEL_26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x78C,
    (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
    (const char *)(unsigned int)v5,
    NewElement);
LABEL_26:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
  return v6;
}

```

## disassembly

```asm
0x1800158f0  mov     [rsp-18h+arg_10], rbx
0x1800158f5  mov     [rsp-18h+arg_18], rdi
0x1800158fa  push    rbp
0x1800158fb  push    r14
0x1800158fd  push    r15
0x1800158ff  mov     rbp, rsp
0x180015902  sub     rsp, 70h
0x180015906  mov     rax, cs:__security_cookie
0x18001590d  xor     rax, rsp
0x180015910  mov     [rbp+var_10], rax
0x180015914  mov     [rbp+var_48], ecx
0x180015917  lea     rbx, SRWLock
0x18001591e  mov     rcx, rbx; SRWLock
0x180015921  mov     r14, rdx
0x180015924  call    cs:__imp_AcquireSRWLockExclusive
0x18001592a  lea     rax, [rbp+var_48]
0x18001592e  mov     [rbp+var_30], rbx
0x180015932  xor     r15d, r15d
0x180015935  mov     [rbp+Buffer], rax
0x180015939  lea     rdx, [rbp+Buffer]; Buffer
0x18001593d  mov     [rbp+var_38], r15
0x180015941  lea     rcx, ?s_volumeCache@VolumeManager@Deployment@Common@@0V?$GenericMap@PEAIPEAVVolume@Deployment@Common@@@3@A; Table
0x180015948  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18001594e  test    rax, rax
0x180015951  jz      short loc_18001598B
0x180015953  mov     rcx, [rax+8]; this
0x180015957  test    rcx, rcx
0x18001595a  jz      short loc_18001598B
0x18001595c  mov     rdx, r14; struct Common::Deployment::Volume *
0x18001595f  call    ?CopyTo@Volume@Deployment@Common@@QEBAJPEAV123@@Z; Common::Deployment::Volume::CopyTo(Common::Deployment::Volume *)
0x180015964  mov     ebx, eax
0x180015966  test    eax, eax
0x180015968  jns     loc_180015AC1
0x18001596e  mov     rcx, [rbp+18h]; this
0x180015972  lea     r8, aOnecoreAdminAp_12; "onecore\\admin\\appmodel\\common\\volum"...
0x180015979  mov     r9d, eax; char *
0x18001597c  mov     edx, 78Ch; void *
0x180015981  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015986  jmp     loc_180015B37
0x18001598b  lea     rdx, [rbp+Buffer]; void **
0x18001598f  mov     [rbp+Buffer], r15
0x180015993  mov     ecx, 70h ; 'p'; Size
0x180015998  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x18001599d  mov     rbx, [rbp+Buffer]
0x1800159a1  test    rbx, rbx
0x1800159a4  jz      loc_180015B11
0x1800159aa  mov     [rbx], r15
0x1800159ad  lea     r9, [rbp+Buffer]; unsigned int *
0x1800159b1  mov     [rbx+18h], r15
0x1800159b5  lea     rdx, [rbp+var_28]; unsigned __int16 *
0x1800159b9  xorps   xmm0, xmm0
0x1800159bc  xor     eax, eax
0x1800159be  movups  xmmword ptr [rbx+8], xmm0
0x1800159c2  mov     [rbx+30h], r15
0x1800159c6  movups  xmmword ptr [rbx+20h], xmm0
0x1800159ca  mov     [rbx+48h], r15
0x1800159ce  movups  xmmword ptr [rbx+38h], xmm0
0x1800159d2  mov     [rbx+60h], r15
0x1800159d6  movups  xmmword ptr [rbx+50h], xmm0
0x1800159da  mov     [rbx+68h], r15w
0x1800159df  mov     ecx, [rbp+var_48]; unsigned int
0x1800159e2  movups  xmmword ptr [rbp+var_28], xmm0
0x1800159e6  mov     qword ptr [rbp+var_28+0Eh], rax
0x1800159ea  call    ?Encode@UInt32@Common@@SAJKPEAGKPEAK@Z; Common::UInt32::Encode(ulong,ushort *,ulong,ulong *)
0x1800159ef  mov     edi, eax
0x1800159f1  test    eax, eax
0x1800159f3  jns     short loc_180015A0F
0x1800159f5  mov     rcx, [rbp+18h]; this
0x1800159f9  lea     r8, aOnecoreAdminAp_12; "onecore\\admin\\appmodel\\common\\volum"...
0x180015a00  mov     r9d, eax; char *
0x180015a03  mov     edx, 856h; void *
0x180015a08  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015a0d  jmp     short loc_180015A21
0x180015a0f  mov     rdx, rbx; struct Common::Deployment::Volume *
0x180015a12  lea     rcx, [rbp+var_28]; unsigned __int16 *
0x180015a16  call    ?ReadVolume@VolumeManager@Deployment@Common@@CAJPEBGPEAVVolume@23@@Z; Common::Deployment::VolumeManager::ReadVolume(ushort const *,Common::Deployment::Volume *)
0x180015a1b  mov     edi, eax
0x180015a1d  test    eax, eax
0x180015a1f  jns     short loc_180015A41
0x180015a21  mov     edx, 792h; void *
0x180015a26  mov     rcx, [rbp+18h]; this
0x180015a2a  lea     r8, aOnecoreAdminAp_12; "onecore\\admin\\appmodel\\common\\volum"...
0x180015a31  mov     r9d, edi; char *
0x180015a34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015a39  mov     rcx, rbx
0x180015a3c  jmp     loc_180015B30
0x180015a41  mov     rdx, r14; struct Common::Deployment::Volume *
0x180015a44  mov     rcx, rbx; this
0x180015a47  call    ?CopyTo@Volume@Deployment@Common@@QEBAJPEAV123@@Z; Common::Deployment::Volume::CopyTo(Common::Deployment::Volume *)
0x180015a4c  mov     edi, eax
0x180015a4e  test    eax, eax
0x180015a50  jns     short loc_180015A59
0x180015a52  mov     edx, 798h
0x180015a57  jmp     short loc_180015A26
0x180015a59  lea     rdx, [rbp+Buffer]; void **
0x180015a5d  mov     [rbp+Buffer], r15
0x180015a61  mov     ecx, 4; Size
0x180015a66  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x180015a6b  mov     r14, [rbp+Buffer]
0x180015a6f  test    r14, r14
0x180015a72  jz      short loc_180015AF0
0x180015a74  mov     eax, [rbp+var_48]
0x180015a77  lea     r9, [rbp+NewElement]; NewElement
0x180015a7b  mov     r8d, 10h; BufferSize
0x180015a81  mov     [r14], eax
0x180015a84  lea     rdx, [rbp+Buffer]; Buffer
0x180015a88  mov     [rbp+Buffer], r14
0x180015a8c  lea     rcx, ?s_volumeCache@VolumeManager@Deployment@Common@@0V?$GenericMap@PEAIPEAVVolume@Deployment@Common@@@3@A; Table
0x180015a93  mov     [rbp+var_38], rbx
0x180015a97  mov     byte ptr [rbp+NewElement], r15b
0x180015a9b  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180015aa1  test    rax, rax
0x180015aa4  jz      short loc_180015AC6
0x180015aa6  cmp     byte ptr [rbp+NewElement], r15b
0x180015aaa  jnz     short loc_180015AB3
0x180015aac  mov     edi, 800702BAh
0x180015ab1  jmp     short loc_180015ACB
0x180015ab3  xor     ecx, ecx; void *
0x180015ab5  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180015aba  xor     ecx, ecx
0x180015abc  call    ??$DeallocateRaw@PEAVVolume@Deployment@Common@@@Common@@YAXPEAVVolume@Deployment@0@@Z; Common::DeallocateRaw<Common::Deployment::Volume *>(Common::Deployment::Volume *)
0x180015ac1  mov     ebx, r15d
0x180015ac4  jmp     short loc_180015B37
0x180015ac6  mov     edi, 8007000Eh
0x180015acb  mov     rcx, [rbp+18h]; this
0x180015acf  lea     r8, aOnecoreAdminAp_12; "onecore\\admin\\appmodel\\common\\volum"...
0x180015ad6  mov     r9d, edi; char *
0x180015ad9  mov     edx, 79Ch; void *
0x180015ade  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015ae3  mov     rcx, r14; void *
0x180015ae6  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180015aeb  jmp     loc_180015A39
0x180015af0  mov     rcx, [rbp+18h]; this
0x180015af4  lea     r8, aOnecoreAdminAp_12; "onecore\\admin\\appmodel\\common\\volum"...
0x180015afb  mov     edi, 8007000Eh
0x180015b00  mov     edx, 79Bh; void *
0x180015b05  mov     r9d, edi; char *
0x180015b08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015b0d  xor     ecx, ecx
0x180015b0f  jmp     short loc_180015AE6
0x180015b11  mov     rcx, [rbp+18h]; this
0x180015b15  lea     r8, aOnecoreAdminAp_12; "onecore\\admin\\appmodel\\common\\volum"...
0x180015b1c  mov     edi, 8007000Eh
0x180015b21  mov     edx, 791h; void *
0x180015b26  mov     r9d, edi; char *
0x180015b29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015b2e  xor     ecx, ecx
0x180015b30  call    ??$DeallocateRaw@PEAVVolume@Deployment@Common@@@Common@@YAXPEAVVolume@Deployment@0@@Z; Common::DeallocateRaw<Common::Deployment::Volume *>(Common::Deployment::Volume *)
0x180015b35  mov     ebx, edi
0x180015b37  lea     rcx, [rbp+var_30]
0x180015b3b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015b40  mov     eax, ebx
0x180015b42  mov     rcx, [rbp+var_10]
0x180015b46  xor     rcx, rsp; StackCookie
0x180015b49  call    __security_check_cookie
0x180015b4e  lea     r11, [rsp+70h+var_s0]
0x180015b53  mov     rbx, [r11+30h]
0x180015b57  mov     rdi, [r11+38h]
0x180015b5b  mov     rsp, r11
0x180015b5e  pop     r15
0x180015b60  pop     r14
0x180015b62  pop     rbp
0x180015b63  retn
```
