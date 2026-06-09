# AssembleCurrentConfigBlob(_DTV_Audio_Playback_Modes,tagVARIANT *)

- ea: `0x18000b900`
- end: `0x18000bd09`
- name: `?AssembleCurrentConfigBlob@@YAJU_DTV_Audio_Playback_Modes@@PEAUtagVARIANT@@@Z`
- size: `1033`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180010060`

## callees

- `0x180001360`
- `0x1800013a0`
- `0x1800017b0`
- `0x1800021a8`
- `0x18000b900`
- `0x18001fe90`
- `0x180022130`
- `0x180023e40`
- `0x180024fd0`
- `0x180033080`
- `0x180049fa8`
- `0x1800886fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bc7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bc7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bbc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bbc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bbb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bbb1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000b97b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000b97b`

## pseudocode

```c
__int64 __fastcall AssembleCurrentConfigBlob(int a1, __int64 a2)
{
  __int64 v2; // r13
  void *v4; // r14
  unsigned int appended; // ebx
  char *v6; // rdi
  unsigned int v7; // ebx
  char *v8; // rax
  unsigned int v9; // r15d
  unsigned int v10; // esi
  char *v11; // rax
  char *v12; // rbx
  CMFRSA *v13; // rcx
  int v14; // r15d
  unsigned int v15; // esi
  int v16; // eax
  void *v17; // r12
  unsigned int v18; // eax
  HANDLE ProcessHeap; // rax
  void *v20; // rax
  void *v21; // rbx
  unsigned int v22; // eax
  SIZE_T v23; // rcx
  size_t v24; // rdi
  void *v25; // rax
  int v26; // [rsp+30h] [rbp-59h] BYREF
  void *Src; // [rsp+38h] [rbp-51h]
  size_t Size; // [rsp+40h] [rbp-49h]
  SIZE_T cb; // [rsp+48h] [rbp-41h]
  unsigned int v30[2]; // [rsp+50h] [rbp-39h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-31h] BYREF
  unsigned __int8 v32[8]; // [rsp+60h] [rbp-29h] BYREF
  unsigned __int8 v33[4]; // [rsp+68h] [rbp-21h] BYREF
  int v34; // [rsp+6Ch] [rbp-1Dh]
  GUID v35; // [rsp+70h] [rbp-19h]
  __int128 v36; // [rsp+80h] [rbp-9h]
  unsigned __int8 v37[16]; // [rsp+90h] [rbp+7h] BYREF

  *(_QWORD *)v30 = a2;
  *(_DWORD *)v32 = a1;
  v2 = a2;
  *(_OWORD *)v37 = 0;
  if ( !a2 )
    return 2147500035LL;
  v36 = xmmword_18008DC10;
  v35 = CLSID_CMPEG2AudDecoderDS;
  *(_DWORD *)v33 = 188;
  v34 = 1;
  *(_QWORD *)v37 = GetTickCount();
  if ( (unsigned int)WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Decrypt()
    || (unsigned int)WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Decrypt() )
  {
    return 2147549183LL;
  }
  v26 = 0;
  Src = 0;
  v4 = 0;
  Size = 0;
  LODWORD(cb) = 0;
  appended = BlobContainer::AppendData((BlobContainer *)&v26, v33, 0x28u);
  if ( appended )
    goto LABEL_42;
  appended = BlobContainer::AppendData((BlobContainer *)&v26, v37, 8u);
  if ( appended )
    goto LABEL_42;
  v6 = (char *)Src;
  lpMem = (LPVOID)0x400000000LL;
  if ( v26 )
  {
    appended = -2147467259;
    goto LABEL_43;
  }
  if ( Src )
  {
    v9 = HIDWORD(Size);
    v7 = Size;
  }
  else
  {
    v7 = 4096;
    v8 = (char *)operator new(0x1000u);
    Src = v8;
    v6 = v8;
    if ( !v8 )
    {
      appended = -2147024882;
      goto LABEL_43;
    }
    LODWORD(Size) = 4096;
    v9 = 0;
    memset_0(v8, 0, 0x1000u);
  }
  v10 = v9 + 8;
  if ( v9 >= 0xFFFFFFF8 )
    goto LABEL_15;
  if ( v10 >= 0x2000 )
  {
    appended = -2147467259;
    goto LABEL_43;
  }
  if ( v10 > v7 )
  {
    v11 = (char *)operator new(2 * v10);
    v12 = v11;
    if ( !v11 )
    {
      v2 = *(_QWORD *)v30;
      appended = -2147024882;
      goto LABEL_43;
    }
    memset_0(v11, 0, 2 * v10);
    memcpy_0(v12, v6, v9);
    operator delete(v6);
    v2 = *(_QWORD *)v30;
    v6 = v12;
    LODWORD(Size) = 2 * v10;
    Src = v12;
  }
  HIDWORD(Size) = v9 + 8;
  *(_QWORD *)&v6[v9] = lpMem;
  appended = BlobContainer::AppendData((BlobContainer *)&v26, v32, 4u);
  if ( appended )
  {
LABEL_42:
    v6 = (char *)Src;
    goto LABEL_43;
  }
  v14 = v26;
  v6 = (char *)Src;
  v30[0] = 0;
  lpMem = 0;
  if ( v26 || (v15 = HIDWORD(Size)) == 0 || !Src )
  {
    appended = -2147467259;
    goto LABEL_43;
  }
  v16 = CMFRSA::MFRsaSign(
          v13,
          (void *)&g_MPEG2_AudioPrivateKeyRC4,
          (const unsigned __int8 *)Src,
          HIDWORD(Size),
          (unsigned __int8 **)&lpMem,
          v30);
  v17 = lpMem;
  appended = v16;
  if ( v16 >= 0 )
  {
    if ( !lpMem )
    {
      appended = -2147418113;
      goto LABEL_34;
    }
    v18 = BlobContainer::AppendData((BlobContainer *)&v26, (unsigned __int8 *)lpMem, v30[0]);
    v14 = v26;
    v15 = HIDWORD(Size);
    appended = v18;
    v6 = (char *)Src;
    if ( !v18 )
      v14 = 1;
  }
  if ( v17 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v17);
  }
LABEL_34:
  if ( !appended )
  {
    LODWORD(cb) = 0;
    if ( v14 == 1 )
    {
      if ( !v6 || !v15 )
      {
LABEL_15:
        appended = -2147418113;
        goto LABEL_43;
      }
      v20 = operator new(v15);
      v21 = v20;
      if ( v20 )
      {
        memcpy_0(v20, v6, v15);
        v4 = v21;
        LODWORD(cb) = v15;
        appended = 0;
      }
      else
      {
        appended = -2147024882;
      }
    }
    else
    {
      appended = -2147467259;
    }
  }
LABEL_43:
  if ( v6 )
    operator delete(v6);
  if ( (unsigned int)WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Encrypt()
    || (unsigned int)WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Encrypt() )
  {
    return 2147549183LL;
  }
  if ( !appended )
  {
    if ( v4 )
    {
      v22 = cb;
      if ( (_DWORD)cb )
      {
        v23 = (unsigned int)cb;
        *(_WORD *)v2 = 16400;
        v24 = v22;
        v25 = CoTaskMemAlloc(v23);
        *(_QWORD *)(v2 + 8) = v25;
        if ( v25 )
        {
          memcpy_0(v25, v4, v24);
          operator delete(v4);
          return 0;
        }
        else
        {
          operator delete(v4);
          return 2147942414LL;
        }
      }
    }
    appended = -2147418113;
  }
  if ( v4 )
    operator delete(v4);
  return appended;
}

```

## disassembly

```asm
0x18000b900  push    rbp
0x18000b902  push    r13
0x18000b904  lea     rbp, [rsp-4Fh]
0x18000b909  sub     rsp, 0D8h
0x18000b910  mov     rax, cs:__security_cookie
0x18000b917  xor     rax, rsp
0x18000b91a  mov     [rbp+57h+var_40], rax
0x18000b91e  mov     qword ptr [rbp+57h+var_90], rdx
0x18000b922  xorps   xmm0, xmm0
0x18000b925  mov     dword ptr [rbp+57h+var_80], ecx
0x18000b928  mov     r13, rdx
0x18000b92b  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x18000b930  test    rdx, rdx
0x18000b933  jnz     short loc_18000B93F
0x18000b935  mov     eax, 80004003h
0x18000b93a  jmp     loc_18000BCF1
0x18000b93f  movups  xmm0, cs:xmmword_18008DC10
0x18000b946  mov     [rsp+0E0h+arg_10], rbx
0x18000b94e  movups  xmm1, xmmword ptr cs:CLSID_CMPEG2AudDecoderDS.Data1
0x18000b955  mov     [rsp+0E0h+var_18], rdi
0x18000b95d  movups  [rbp+57h+var_60], xmm0
0x18000b961  mov     [rsp+0E0h+var_28], r14
0x18000b969  movups  [rbp+57h+var_70], xmm1
0x18000b96d  mov     dword ptr [rbp+57h+var_78], 0BCh
0x18000b974  mov     [rbp+57h+var_74], 1
0x18000b97b  call    cs:__imp_GetTickCount
0x18000b982  nop     dword ptr [rax+rax+00h]
0x18000b987  mov     eax, eax
0x18000b989  mov     qword ptr [rbp+57h+var_50], rax
0x18000b98d  call    ?Decrypt@?$CEncryption@$0A@V?$CCipherFeistel64@$0BC@$0GD@$0EK@$0OP@$0BE@$0OE@$0CF@$0MC@$0BO@$0FO@$0HK@$0EN@$0BJ@$0HG@$0PI@$0OK@$0BG@$0PH@$0CF@$0JN@$00$03$0N@$0BE@$07$0HP@$07$0NI@$0L@$0BN@$0FB@$0EK@$09$0OH@$0HF@$0BM@$01$0NF@$0ND@$0FG@@WarbirdCrypto@@V?$CHashFunctionSCP@$01$02$0A@$0?BMINLIEJLPHNNHJC@@2@UENCRYPTED_SEGMENT_DATA_CONST_1@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_1@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_1@2@@Z; WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Decrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1 *)
0x18000b992  test    eax, eax
0x18000b994  jnz     loc_18000BCD4
0x18000b99a  call    ?Decrypt@?$CEncryption@$00V?$CCipherFeistel64@$0BD@$0PI@$0LF@$0EG@$09$0CD@$0BC@$0LG@$05$0NJ@$0DI@$0CM@$0BI@$0KC@$0NB@$0JF@$0BA@$0NF@$0NO@$0LH@$0BE@$0CD@$0DD@$0CI@$0BN@$0IL@$0HD@$0NF@$0M@$0OE@$0BK@$0PN@$03$0FI@$0HI@$0DF@$0BF@$0OF@$0CP@$0OD@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$0A@$0ENFLKLIPNEIOMFLN@@2@UENCRYPTED_SEGMENT_DATA_CONST_2@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_2@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_2@2@@Z; WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Decrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2 *)
0x18000b99f  test    eax, eax
0x18000b9a1  jnz     loc_18000BCD4
0x18000b9a7  mov     [rsp+0E0h+var_10], rsi
0x18000b9af  lea     rdx, [rbp+57h+var_78]; unsigned __int8 *
0x18000b9b3  mov     [rsp+0E0h+var_20], r12
0x18000b9bb  lea     rcx, [rbp+57h+var_B0]; this
0x18000b9bf  xor     r12d, r12d
0x18000b9c2  mov     [rsp+0E0h+var_30], r15
0x18000b9ca  mov     r8d, 28h ; '('; unsigned int
0x18000b9d0  mov     [rbp+57h+var_B0], r12d
0x18000b9d4  mov     [rbp+57h+Src], r12
0x18000b9d8  mov     r14d, r12d
0x18000b9db  mov     [rbp+57h+Size], r12
0x18000b9df  mov     dword ptr [rbp+57h+cb], r12d
0x18000b9e3  call    ?AppendData@BlobContainer@@QEAAJPEAEK@Z; BlobContainer::AppendData(uchar *,ulong)
0x18000b9e8  mov     ebx, eax
0x18000b9ea  test    eax, eax
0x18000b9ec  jnz     loc_18000BC28
0x18000b9f2  mov     r8d, 8; unsigned int
0x18000b9f8  lea     rdx, [rbp+57h+var_50]; unsigned __int8 *
0x18000b9fc  lea     rcx, [rbp+57h+var_B0]; this
0x18000ba00  call    ?AppendData@BlobContainer@@QEAAJPEAEK@Z; BlobContainer::AppendData(uchar *,ulong)
0x18000ba05  mov     ebx, eax
0x18000ba07  test    eax, eax
0x18000ba09  jnz     loc_18000BC28
0x18000ba0f  mov     rdi, [rbp+57h+Src]
0x18000ba13  mov     dword ptr [rbp+57h+lpMem+4], 4
0x18000ba1a  mov     dword ptr [rbp+57h+lpMem], r12d
0x18000ba1e  cmp     [rbp+57h+var_B0], r12d
0x18000ba22  jz      short loc_18000BA2E
0x18000ba24  mov     ebx, 80004005h
0x18000ba29  jmp     loc_18000BC2C
0x18000ba2e  test    rdi, rdi
0x18000ba31  jnz     short loc_18000BA6A
0x18000ba33  mov     ebx, 1000h
0x18000ba38  mov     ecx, ebx; Size
0x18000ba3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ba3f  mov     [rbp+57h+Src], rax
0x18000ba43  mov     rdi, rax
0x18000ba46  test    rax, rax
0x18000ba49  jnz     short loc_18000BA55
0x18000ba4b  mov     ebx, 8007000Eh
0x18000ba50  jmp     loc_18000BC2C
0x18000ba55  mov     r8, rbx; Size
0x18000ba58  mov     dword ptr [rbp+57h+Size], ebx
0x18000ba5b  xor     edx, edx; Val
0x18000ba5d  mov     rcx, rax; void *
0x18000ba60  mov     r15d, r12d
0x18000ba63  call    memset_0
0x18000ba68  jmp     short loc_18000BA71
0x18000ba6a  mov     r15d, dword ptr [rbp+57h+Size+4]
0x18000ba6e  mov     ebx, dword ptr [rbp+57h+Size]
0x18000ba71  lea     esi, [r15+8]
0x18000ba75  cmp     esi, 8
0x18000ba78  jnb     short loc_18000BA84
0x18000ba7a  mov     ebx, 8000FFFFh
0x18000ba7f  jmp     loc_18000BC2C
0x18000ba84  cmp     esi, 2000h
0x18000ba8a  jb      short loc_18000BA96
0x18000ba8c  mov     ebx, 80004005h
0x18000ba91  jmp     loc_18000BC2C
0x18000ba96  cmp     esi, ebx
0x18000ba98  jbe     short loc_18000BAF4
0x18000ba9a  lea     r12d, [rsi+rsi]
0x18000ba9e  mov     ecx, r12d; Size
0x18000baa1  mov     r13d, r12d
0x18000baa4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000baa9  mov     rbx, rax
0x18000baac  test    rax, rax
0x18000baaf  jnz     short loc_18000BABF
0x18000bab1  mov     r13, qword ptr [rbp+57h+var_90]
0x18000bab5  mov     ebx, 8007000Eh
0x18000baba  jmp     loc_18000BC2C
0x18000babf  mov     r8, r13; Size
0x18000bac2  xor     edx, edx; Val
0x18000bac4  mov     rcx, rbx; void *
0x18000bac7  call    memset_0
0x18000bacc  mov     r8d, r15d; Size
0x18000bacf  mov     rdx, rdi; Src
0x18000bad2  mov     rcx, rbx; void *
0x18000bad5  call    memcpy_0
0x18000bada  mov     rcx, rdi; Block
0x18000badd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bae2  mov     r13, qword ptr [rbp+57h+var_90]
0x18000bae6  mov     rdi, rbx
0x18000bae9  mov     dword ptr [rbp+57h+Size], r12d
0x18000baed  xor     r12d, r12d
0x18000baf0  mov     [rbp+57h+Src], rbx
0x18000baf4  mov     rax, [rbp+57h+lpMem]
0x18000baf8  lea     rdx, [rbp+57h+var_80]; unsigned __int8 *
0x18000bafc  mov     ecx, r15d
0x18000baff  mov     r8d, 4; unsigned int
0x18000bb05  mov     dword ptr [rbp+57h+Size+4], esi
0x18000bb08  mov     [rcx+rdi], rax
0x18000bb0c  lea     rcx, [rbp+57h+var_B0]; this
0x18000bb10  call    ?AppendData@BlobContainer@@QEAAJPEAEK@Z; BlobContainer::AppendData(uchar *,ulong)
0x18000bb15  mov     ebx, eax
0x18000bb17  test    eax, eax
0x18000bb19  jnz     loc_18000BC28
0x18000bb1f  mov     r15d, [rbp+57h+var_B0]
0x18000bb23  mov     rdi, [rbp+57h+Src]
0x18000bb27  mov     [rbp+57h+var_90], r12d
0x18000bb2b  mov     [rbp+57h+lpMem], r12
0x18000bb2f  test    r15d, r15d
0x18000bb32  jz      short loc_18000BB3E
0x18000bb34  mov     ebx, 80004005h
0x18000bb39  jmp     loc_18000BC2C
0x18000bb3e  mov     esi, dword ptr [rbp+57h+Size+4]
0x18000bb41  test    esi, esi
0x18000bb43  jz      short loc_18000BB34
0x18000bb45  test    rdi, rdi
0x18000bb48  jz      short loc_18000BB34
0x18000bb4a  lea     rax, [rbp+57h+var_90]
0x18000bb4e  mov     r9d, esi; unsigned int
0x18000bb51  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x18000bb56  lea     rdx, ?g_MPEG2_AudioPrivateKeyRC4@@3QBEB; void *
0x18000bb5d  lea     rax, [rbp+57h+lpMem]
0x18000bb61  mov     r8, rdi; unsigned __int8 *
0x18000bb64  mov     [rsp+0E0h+var_C0], rax; unsigned __int8 **
0x18000bb69  call    ?MFRsaSign@CMFRSA@@QEAAJPEAXPEBEKPEAPEAEPEAK@Z; CMFRSA::MFRsaSign(void *,uchar const *,ulong,uchar * *,ulong *)
0x18000bb6e  mov     r12, [rbp+57h+lpMem]
0x18000bb72  mov     ebx, eax
0x18000bb74  test    eax, eax
0x18000bb76  js      short loc_18000BBAC
0x18000bb78  test    r12, r12
0x18000bb7b  jnz     short loc_18000BB84
0x18000bb7d  mov     ebx, 8000FFFFh
0x18000bb82  jmp     short loc_18000BBD1
0x18000bb84  mov     r8d, [rbp+57h+var_90]; unsigned int
0x18000bb88  lea     rcx, [rbp+57h+var_B0]; this
0x18000bb8c  mov     rdx, r12; unsigned __int8 *
0x18000bb8f  call    ?AppendData@BlobContainer@@QEAAJPEAEK@Z; BlobContainer::AppendData(uchar *,ulong)
0x18000bb94  mov     r15d, [rbp+57h+var_B0]
0x18000bb98  test    eax, eax
0x18000bb9a  mov     esi, dword ptr [rbp+57h+Size+4]
0x18000bb9d  mov     ebx, eax
0x18000bb9f  mov     rdi, [rbp+57h+Src]
0x18000bba3  mov     eax, 1
0x18000bba8  cmovz   r15d, eax
0x18000bbac  test    r12, r12
0x18000bbaf  jz      short loc_18000BBD1
0x18000bbb1  call    cs:__imp_GetProcessHeap
0x18000bbb8  nop     dword ptr [rax+rax+00h]
0x18000bbbd  mov     r8, r12; lpMem
0x18000bbc0  xor     edx, edx; dwFlags
0x18000bbc2  mov     rcx, rax; hHeap
0x18000bbc5  call    cs:__imp_HeapFree
0x18000bbcc  nop     dword ptr [rax+rax+00h]
0x18000bbd1  test    ebx, ebx
0x18000bbd3  jnz     short loc_18000BC2C
0x18000bbd5  mov     dword ptr [rbp+57h+cb], r14d
0x18000bbd9  cmp     r15d, 1
0x18000bbdd  jz      short loc_18000BBE6
0x18000bbdf  mov     ebx, 80004005h
0x18000bbe4  jmp     short loc_18000BC2C
0x18000bbe6  test    rdi, rdi
0x18000bbe9  jz      loc_18000BA7A
0x18000bbef  test    esi, esi
0x18000bbf1  jz      loc_18000BA7A
0x18000bbf7  mov     ecx, esi; Size
0x18000bbf9  mov     r15d, esi
0x18000bbfc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bc01  mov     rbx, rax
0x18000bc04  test    rax, rax
0x18000bc07  jnz     short loc_18000BC10
0x18000bc09  mov     ebx, 8007000Eh
0x18000bc0e  jmp     short loc_18000BC2C
0x18000bc10  mov     r8, r15; Size
0x18000bc13  mov     rdx, rdi; Src
0x18000bc16  mov     rcx, rbx; void *
0x18000bc19  call    memcpy_0
0x18000bc1e  mov     r14, rbx
0x18000bc21  mov     dword ptr [rbp+57h+cb], esi
0x18000bc24  xor     ebx, ebx
0x18000bc26  jmp     short loc_18000BC2C
0x18000bc28  mov     rdi, [rbp+57h+Src]
0x18000bc2c  mov     r15, [rsp+0E0h+var_30]
0x18000bc34  mov     r12, [rsp+0E0h+var_20]
0x18000bc3c  mov     rsi, [rsp+0E0h+var_10]
0x18000bc44  test    rdi, rdi
0x18000bc47  jz      short loc_18000BC51
0x18000bc49  mov     rcx, rdi; Block
0x18000bc4c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bc51  call    ?Encrypt@?$CEncryption@$0A@V?$CCipherFeistel64@$0BC@$0GD@$0EK@$0OP@$0BE@$0OE@$0CF@$0MC@$0BO@$0FO@$0HK@$0EN@$0BJ@$0HG@$0PI@$0OK@$0BG@$0PH@$0CF@$0JN@$00$03$0N@$0BE@$07$0HP@$07$0NI@$0L@$0BN@$0FB@$0EK@$09$0OH@$0HF@$0BM@$01$0NF@$0ND@$0FG@@WarbirdCrypto@@V?$CHashFunctionSCP@$01$02$0A@$0?BMINLIEJLPHNNHJC@@2@UENCRYPTED_SEGMENT_DATA_CONST_1@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_1@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_1@2@@Z; WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Encrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1 *)
0x18000bc56  test    eax, eax
0x18000bc58  jnz     short loc_18000BCD4
0x18000bc5a  call    ?Encrypt@?$CEncryption@$00V?$CCipherFeistel64@$0BD@$0PI@$0LF@$0EG@$09$0CD@$0BC@$0LG@$05$0NJ@$0DI@$0CM@$0BI@$0KC@$0NB@$0JF@$0BA@$0NF@$0NO@$0LH@$0BE@$0CD@$0DD@$0CI@$0BN@$0IL@$0HD@$0NF@$0M@$0OE@$0BK@$0PN@$03$0FI@$0HI@$0DF@$0BF@$0OF@$0CP@$0OD@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$0A@$0ENFLKLIPNEIOMFLN@@2@UENCRYPTED_SEGMENT_DATA_CONST_2@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_2@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_2@2@@Z; WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Encrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2 *)
0x18000bc5f  test    eax, eax
0x18000bc61  jnz     short loc_18000BCD4
0x18000bc63  test    ebx, ebx
0x18000bc65  jnz     short loc_18000BCC3
0x18000bc67  test    r14, r14
0x18000bc6a  jz      short loc_18000BCBE
0x18000bc6c  mov     eax, dword ptr [rbp+57h+cb]
0x18000bc6f  test    eax, eax
0x18000bc71  jz      short loc_18000BCBE
0x18000bc73  mov     ecx, eax; cb
0x18000bc75  mov     word ptr [r13+0], 4010h
0x18000bc7c  mov     edi, eax
0x18000bc7e  call    cs:__imp_CoTaskMemAlloc
0x18000bc85  nop     dword ptr [rax+rax+00h]
0x18000bc8a  mov     [r13+8], rax
0x18000bc8e  test    rax, rax
0x18000bc91  jnz     short loc_18000BCA4
0x18000bc93  mov     rcx, r14; Block
0x18000bc96  mov     ebx, 8007000Eh
0x18000bc9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bca0  mov     eax, ebx
0x18000bca2  jmp     short loc_18000BCD9
0x18000bca4  mov     r8, rdi; Size
0x18000bca7  mov     rdx, r14; Src
0x18000bcaa  mov     rcx, rax; void *
0x18000bcad  call    memcpy_0
0x18000bcb2  mov     rcx, r14; Block
0x18000bcb5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bcba  mov     eax, ebx
0x18000bcbc  jmp     short loc_18000BCD9
0x18000bcbe  mov     ebx, 8000FFFFh
0x18000bcc3  test    r14, r14
0x18000bcc6  jz      short loc_18000BCD0
0x18000bcc8  mov     rcx, r14; Block
0x18000bccb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bcd0  mov     eax, ebx
0x18000bcd2  jmp     short loc_18000BCD9
0x18000bcd4  mov     eax, 8000FFFFh
0x18000bcd9  mov     rdi, [rsp+0E0h+var_18]
0x18000bce1  mov     rbx, [rsp+0E0h+arg_10]
0x18000bce9  mov     r14, [rsp+0E0h+var_28]
0x18000bcf1  mov     rcx, [rbp+57h+var_40]
0x18000bcf5  xor     rcx, rsp; StackCookie
0x18000bcf8  call    __security_check_cookie
0x18000bcfd  add     rsp, 0D8h
0x18000bd04  pop     r13
0x18000bd06  pop     rbp
0x18000bd07  retn
```
