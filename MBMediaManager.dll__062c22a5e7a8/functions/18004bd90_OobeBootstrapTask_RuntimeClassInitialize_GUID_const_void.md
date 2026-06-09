# OobeBootstrapTask::RuntimeClassInitialize(_GUID const &,void * *)

- ea: `0x18004bd90`
- end: `0x18004be80`
- name: `?RuntimeClassInitialize@OobeBootstrapTask@@QEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `240`
- prototype: `__int64 __fastcall(OobeBootstrapTask *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034560`

## callees

- `0x180002150`
- `0x18001cb10`
- `0x18004bd90`
- `0x18004c950`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004bdda`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004bdda`

## pseudocode

```c
__int64 __fastcall OobeBootstrapTask::RuntimeClassInitialize(
        OobeBootstrapTask *this,
        const struct _GUID *a2,
        void **a3)
{
  LPVOID *v4; // rsi
  HRESULT Instance; // eax
  unsigned int v6; // edi
  __int64 result; // rax
  int v8; // eax
  unsigned int v9; // edi
  const char *v10; // r9
  int EmbeddedSimSlot; // eax
  unsigned int v12; // ebx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(struct _GUID *)((char *)this + 72) = *a2;
  *((_QWORD *)this + 11) = a3;
  *((_DWORD *)this + 24) = 0;
  v4 = (LPVOID *)((char *)this + 16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 16);
  Instance = CoCreateInstance(
               &GUID_25d7baff_f559_4d0e_9ea4_b48f936956aa,
               0,
               1u,
               &GUID_99551656_c20f_4840_a833_989d2e861f06,
               v4);
  v6 = Instance;
  if ( Instance >= 0 )
  {
    try
    {
      v8 = (*(__int64 (**)(void))(*(_QWORD *)*v4 + 24LL))();
      v9 = v8;
      if ( v8 >= 0 )
      {
        EmbeddedSimSlot = MBUtil::GetEmbeddedSimSlot((OobeBootstrapTask *)((char *)this + 100));
        v12 = EmbeddedSimSlot;
        if ( EmbeddedSimSlot >= 0 )
        {
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A,
            (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobebootstraptask.cpp",
            (const char *)(unsigned int)EmbeddedSimSlot,
            ppv);
          result = v12;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobebootstraptask.cpp",
          (const char *)(unsigned int)v8,
          ppv);
        result = v9;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x1E,
                             (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobebootstraptask.cpp",
                             v10);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobebootstraptask.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18004bd90  mov     [rsp+arg_8], rbx
0x18004bd95  mov     [rsp+arg_10], rsi
0x18004bd9a  push    rdi
0x18004bd9b  sub     rsp, 30h
0x18004bd9f  mov     rbx, rcx
0x18004bda2  movups  xmm0, xmmword ptr [rdx]
0x18004bda5  movdqu  xmmword ptr [rcx+48h], xmm0
0x18004bdaa  mov     [rcx+58h], r8
0x18004bdae  mov     dword ptr [rcx+60h], 0
0x18004bdb5  lea     rsi, [rcx+10h]
0x18004bdb9  mov     rcx, rsi
0x18004bdbc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004bdc1  mov     qword ptr [rsp+38h+ppv], rsi; int
0x18004bdc6  lea     r9, _GUID_99551656_c20f_4840_a833_989d2e861f06; riid
0x18004bdcd  xor     edx, edx; pUnkOuter
0x18004bdcf  lea     r8d, [rdx+1]; dwClsContext
0x18004bdd3  lea     rcx, _GUID_25d7baff_f559_4d0e_9ea4_b48f936956aa; rclsid
0x18004bdda  call    cs:__imp_CoCreateInstance
0x18004bde0  mov     edi, eax
0x18004bde2  test    eax, eax
0x18004bde4  jns     short loc_18004BE03
0x18004bde6  mov     rcx, [rsp+38h]; this
0x18004bdeb  mov     r9d, eax; char *
0x18004bdee  lea     r8, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; unsigned int
0x18004bdf5  mov     edx, 15h; void *
0x18004bdfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bdff  mov     eax, edi
0x18004be01  jmp     short loc_18004BE6F
0x18004be03  mov     rcx, [rsi]
0x18004be06  mov     rax, [rcx]
0x18004be09  xor     r8d, r8d
0x18004be0c  mov     rdx, rbx
0x18004be0f  mov     rax, [rax+18h]
0x18004be13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be18  mov     edi, eax
0x18004be1a  test    eax, eax
0x18004be1c  jns     short loc_18004BE3B
0x18004be1e  mov     rcx, [rsp+38h]; this
0x18004be23  mov     r9d, eax; char *
0x18004be26  lea     r8, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; unsigned int
0x18004be2d  mov     edx, 18h; void *
0x18004be32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004be37  mov     eax, edi
0x18004be39  jmp     short loc_18004BE6F
0x18004be3b  lea     rcx, [rbx+64h]; enum SimSlot *
0x18004be3f  call    ?GetEmbeddedSimSlot@MBUtil@@SAJPEAW4SimSlot@@@Z; MBUtil::GetEmbeddedSimSlot(SimSlot *)
0x18004be44  mov     ebx, eax
0x18004be46  test    eax, eax
0x18004be48  jns     short loc_18004BE67
0x18004be4a  mov     rcx, [rsp+38h]; this
0x18004be4f  mov     r9d, eax; char *
0x18004be52  lea     r8, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; unsigned int
0x18004be59  mov     edx, 1Ah; void *
0x18004be5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004be63  mov     eax, ebx
0x18004be65  jmp     short loc_18004BE6F
0x18004be67  xor     eax, eax
0x18004be69  jmp     short loc_18004BE6F
0x18004be6b  mov     eax, [rsp+38h+arg_0]
0x18004be6f  mov     rbx, [rsp+38h+arg_8]
0x18004be74  mov     rsi, [rsp+38h+arg_10]
0x18004be79  add     rsp, 30h
0x18004be7d  pop     rdi
0x18004be7e  retn
```
