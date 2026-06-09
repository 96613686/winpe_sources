# CDevice::OpenSharedHandleByName(ushort const *,ulong,void * *)

- ea: `0x1800f8750`
- end: `0x1800f88b7`
- name: `?OpenSharedHandleByName@CDevice@@UEAAJPEBGKPEAPEAX@Z`
- size: `359`
- prototype: `__int64 __fastcall(CDevice *__hidden this, const unsigned __int16 *, unsigned int, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007df0`
- `0x18000b010`
- `0x180050c08`
- `0x1800f8750`
- `0x180103cec`
- `0x180103d3c`

## import_xrefs

- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTOpenNtHandleFromName` at `0x1800f87c1`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTOpenSyncObjectNtHandleFromName` at `0x1800f8869`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTOpenBundleObjectNtHandleFromName` at `0x1800f8802`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTOpenBundleObjectNtHandleFromName` at `0x1800f8802`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDevice::OpenSharedHandleByName(
        CDevice *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        void **a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r14
  _QWORD *v10; // r15
  __int64 v11; // rbx
  unsigned int v12; // eax
  unsigned int v13; // eax
  int v14; // eax
  __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // eax
  int v19; // ecx
  __int64 result; // rax
  __int64 v21; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+28h] [rbp-A0h]
  void *v23; // [rsp+30h] [rbp-98h]
  _com_error *v24; // [rsp+40h] [rbp-88h] BYREF
  __int64 v25; // [rsp+A8h] [rbp-20h]

  try
  {
    InitObjectAttributesHelper<&public: static long NDXGI::CUMDAdapter::NTStatusToHResult_TranslateToAPIError(long)>::InitObjectAttributesHelper<&public: static long NDXGI::CUMDAdapter::NTStatusToHResult_TranslateToAPIError(long)>();
    v9 = v25;
    *(_DWORD *)(v25 + 24) &= ~2u;
    v10 = (_QWORD *)((char *)this + 760);
    if ( a3 == 0x10000000 )
    {
      v21 = 0x10000000;
      v23 = 0;
      v22 = v9;
      v11 = *v10;
      v12 = CallAndLogImpl<long (*)(_D3DKMT_OPENNTHANDLEFROMNAME *),_D3DKMT_OPENNTHANDLEFROMNAME *>(
              D3DKMTOpenNtHandleFromName,
              v7,
              v8,
              &v21,
              0x10000000,
              v9);
      if ( (int)NDXGI::CDevice::NTStatusToHResult(v11, v12, 1) >= 0 )
      {
LABEL_9:
        *a4 = v23;
        return 0;
      }
      v21 = 0x10000000;
      v23 = 0;
      v22 = v9;
      v13 = D3DKMTOpenBundleObjectNtHandleFromName(&v21);
      v14 = NDXGI::CDevice::NTStatusToHResult(*v10, v13, 1);
      if ( v14 < 0 )
      {
LABEL_8:
        ThrowFailure(a3 != 0x10000000 ? 0x80070057 : 0);
        v23 = 0;
        v21 = a3;
        v22 = v9;
        v15 = *v10;
        v18 = CallAndLogImpl<long (*)(_D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME *),_D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME *>(
                D3DKMTOpenSyncObjectNtHandleFromName,
                v16,
                v17,
                &v21,
                a3,
                v9);
        v19 = NDXGI::CDevice::NTStatusToHResult(v15, v18, 1);
        ThrowFailure(v19);
        goto LABEL_9;
      }
      *a4 = v23;
    }
    else
    {
      v14 = -2147024809;
    }
    if ( v14 >= 0 )
      return 0;
    goto LABEL_8;
  }
  catch ( _com_error *v24 )
  {
    *a4 = 0;
    return *((unsigned int *)v24 + 2);
  }
  return result;
}

```

## disassembly

```asm
0x1800f8750  mov     rax, rsp
0x1800f8753  mov     [rax+8], rbx
0x1800f8757  mov     [rax+10h], rsi
0x1800f875b  mov     [rax+20h], r9
0x1800f875f  push    r12
0x1800f8761  push    r14
0x1800f8763  push    r15
0x1800f8765  sub     rsp, 0B0h
0x1800f876c  mov     rsi, r9
0x1800f876f  mov     r12d, r8d
0x1800f8772  mov     r15, rcx
0x1800f8775  xor     r8d, r8d
0x1800f8778  lea     rcx, [rax-78h]
0x1800f877c  call    ??0?$InitObjectAttributesHelper@$1?NTStatusToHResult_TranslateToAPIError@CUMDAdapter@NDXGI@@SAJJ@Z@@QEAA@PEBGPEBU_SECURITY_ATTRIBUTES@@@Z; InitObjectAttributesHelper<&NDXGI::CUMDAdapter::NTStatusToHResult_TranslateToAPIError(long)>::InitObjectAttributesHelper<&NDXGI::CUMDAdapter::NTStatusToHResult_TranslateToAPIError(long)>(ushort const *,_SECURITY_ATTRIBUTES const *)
0x1800f8781  mov     r14, [rsp+0C8h+var_20]
0x1800f8789  and     dword ptr [r14+18h], 0FFFFFFFDh
0x1800f878e  add     r15, 2F8h
0x1800f8795  cmp     r12d, 10000000h
0x1800f879c  jnz     loc_1800F8826
0x1800f87a2  mov     [rsp+0C8h+var_A8], 10000000h
0x1800f87ab  mov     [rsp+0C8h+var_98], 0
0x1800f87b4  mov     [rsp+0C8h+var_A0], r14
0x1800f87b9  mov     rbx, [r15]
0x1800f87bc  lea     r9, [rsp+0C8h+var_A8]
0x1800f87c1  mov     rcx, cs:__imp_D3DKMTOpenNtHandleFromName
0x1800f87c8  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_OPENNTHANDLEFROMNAME@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_OPENNTHANDLEFROMNAME@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(_D3DKMT_OPENNTHANDLEFROMNAME *),_D3DKMT_OPENNTHANDLEFROMNAME *>(long (*)(_D3DKMT_OPENNTHANDLEFROMNAME *),char const *,RecordStatusFilterResult (*)(long),_D3DKMT_OPENNTHANDLEFROMNAME *)
0x1800f87cd  mov     r8d, 1
0x1800f87d3  mov     edx, eax
0x1800f87d5  mov     rcx, rbx
0x1800f87d8  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CDevice::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x1800f87dd  nop
0x1800f87de  test    eax, eax
0x1800f87e0  jns     loc_1800F888D
0x1800f87e6  mov     [rsp+0C8h+var_A8], 10000000h
0x1800f87ef  mov     [rsp+0C8h+var_98], 0
0x1800f87f8  mov     [rsp+0C8h+var_A0], r14
0x1800f87fd  lea     rcx, [rsp+0C8h+var_A8]
0x1800f8802  call    cs:__imp_D3DKMTOpenBundleObjectNtHandleFromName
0x1800f8808  mov     r8d, 1
0x1800f880e  mov     edx, eax
0x1800f8810  mov     rcx, [r15]
0x1800f8813  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CDevice::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x1800f8818  test    eax, eax
0x1800f881a  js      short loc_1800F882F
0x1800f881c  mov     rcx, [rsp+0C8h+var_98]
0x1800f8821  mov     [rsi], rcx
0x1800f8824  jmp     short loc_1800F882B
0x1800f8826  mov     eax, 80070057h
0x1800f882b  test    eax, eax
0x1800f882d  jns     short loc_1800F8895
0x1800f882f  lea     eax, [r12-10000000h]
0x1800f8837  neg     eax
0x1800f8839  sbb     ecx, ecx
0x1800f883b  and     ecx, 80070057h; int
0x1800f8841  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f8846  mov     dword ptr [rsp+0C8h+var_A8+4], 0
0x1800f884e  mov     [rsp+0C8h+var_98], 0
0x1800f8857  mov     dword ptr [rsp+0C8h+var_A8], r12d
0x1800f885c  mov     [rsp+0C8h+var_A0], r14
0x1800f8861  mov     rbx, [r15]
0x1800f8864  lea     r9, [rsp+0C8h+var_A8]
0x1800f8869  mov     rcx, cs:__imp_D3DKMTOpenSyncObjectNtHandleFromName
0x1800f8870  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(_D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME *),_D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME *>(long (*)(_D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME *),char const *,RecordStatusFilterResult (*)(long),_D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME *)
0x1800f8875  mov     r8d, 1
0x1800f887b  mov     edx, eax
0x1800f887d  mov     rcx, rbx
0x1800f8880  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CDevice::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x1800f8885  nop
0x1800f8886  mov     ecx, eax; int
0x1800f8888  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800f888d  mov     rax, [rsp+0C8h+var_98]
0x1800f8892  mov     [rsi], rax
0x1800f8895  xor     eax, eax
0x1800f8897  jmp     short loc_1800F889D
0x1800f8899  mov     eax, [rsp+0C8h+var_90]
0x1800f889d  lea     r11, [rsp+0C8h+var_18]
0x1800f88a5  mov     rbx, [r11+20h]
0x1800f88a9  mov     rsi, [r11+28h]
0x1800f88ad  mov     rsp, r11
0x1800f88b0  pop     r15
0x1800f88b2  pop     r14
0x1800f88b4  pop     r12
0x1800f88b6  retn
```
