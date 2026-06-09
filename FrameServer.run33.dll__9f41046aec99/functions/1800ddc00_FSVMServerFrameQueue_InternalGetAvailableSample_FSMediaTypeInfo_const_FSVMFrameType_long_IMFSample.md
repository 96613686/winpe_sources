# FSVMServerFrameQueue::InternalGetAvailableSample(FSMediaTypeInfo const &,FSVMFrameType,long,IMFSample * *)

- ea: `0x1800ddc00`
- end: `0x1800de2f2`
- name: `?InternalGetAvailableSample@FSVMServerFrameQueue@@MEAAJAEBUFSMediaTypeInfo@@W4FSVMFrameType@@JPEAPEAUIMFSample@@@Z`
- size: `1778`
- prototype: `int __high(const struct FSMediaTypeInfo *, enum FSVMFrameType, int, struct IMFSample **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180017d90`
- `0x18004d714`
- `0x18004d748`
- `0x1800dcca0`
- `0x1800ddc00`
- `0x1800e15f0`
- `0x1800e17d4`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreateSample` at `0x1800dde44`
- `MFPlat!MFCreateSample` at `0x1800dde44`
- `MFPlat!MFCreateAttributes` at `0x1800ddf21`
- `MFPlat!MFCreateAttributes` at `0x1800ddf21`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800ddeba`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800ddeba`

## pseudocode

```c
__int64 __fastcall FSVMServerFrameQueue::InternalGetAvailableSample(
        __int64 *a1,
        __int64 a2,
        char a3,
        int a4,
        IMFSample **a5)
{
  __int64 v7; // rax
  char v10; // r14
  __int64 (__fastcall *v11)(__int64 *); // rax
  int v12; // ebx
  IMFSample **v13; // r15
  __int64 v14; // rdx
  __int64 v15; // rax
  HRESULT v16; // eax
  __int64 v17; // rdx
  IMFSample *v18; // rcx
  HRESULT v19; // eax
  __int64 v20; // rdx
  IMFMediaBuffer *v21; // rdi
  HRESULT (__stdcall *QueryInterface)(IMFMediaBuffer *, const IID *const, void **); // rbx
  IMFAttributes *v23; // rdi
  HRESULT (__stdcall *v24)(IMFAttributes *, const IID *const, void **); // rbx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rcx
  FSString *v29; // rax
  const char *String; // rax
  bool v31; // zf
  FSString *v32; // rax
  const char *v33; // rax
  __int64 v35; // [rsp+40h] [rbp-51h] BYREF
  __int64 v36; // [rsp+48h] [rbp-49h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+50h] [rbp-41h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+58h] [rbp-39h] BYREF
  IMFSample *ppIMFSample; // [rsp+60h] [rbp-31h] BYREF
  __int64 v40; // [rsp+68h] [rbp-29h] BYREF
  void *v41; // [rsp+70h] [rbp-21h] BYREF
  __int64 v42; // [rsp+78h] [rbp-19h] BYREF
  _BYTE v43[96]; // [rsp+80h] [rbp-11h] BYREF
  int v44; // [rsp+F0h] [rbp+5Fh] BYREF

  v44 = 0;
  v7 = *a1;
  v40 = 0;
  v10 = 0;
  v44 = 0;
  ppIMFSample = 0;
  v11 = *(__int64 (__fastcall **)(__int64 *))(v7 + 56);
  v41 = 0;
  v42 = 0;
  v35 = 0;
  v12 = v11(a1);
  if ( v12 < 0 )
    goto LABEL_68;
  v13 = a5;
  if ( !a5 )
  {
    v12 = -2147467261;
    if ( g_wppLevels )
    {
      v14 = (unsigned int)((_DWORD)a5 + 54);
LABEL_5:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_f5069778e7c6307a26edc2e496375707_Traceguids, a1, v12);
      goto LABEL_68;
    }
    goto LABEL_68;
  }
  *a5 = 0;
  if ( *((_BYTE *)a1 + 96) )
  {
    HIDWORD(v35) = *(_DWORD *)a2;
    v15 = *a1;
    BYTE1(v35) = a3;
    v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64 *, int *))(v15 + 32))(a1, &v35, &v40, &v44);
    if ( v12 < 0 )
      goto LABEL_68;
    if ( BYTE1(v35) == 1 )
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v41);
      v16 = FSVMServerMediaBuffer::Create1DFSVMBuffer(
              (struct IFSVMMediaBufferRelease *)((unsigned __int64)(a1 + 5) & -(__int64)(a1 != 0)),
              (const union FSVMFrameId *)&v35,
              (unsigned __int8 *)(v40 + LODWORD(a1[15 * WORD1(v35) + 21])),
              *((_DWORD *)a1 + 29),
              &GUID_045fa593_8799_42b8_bc8d_8968c6453507,
              &v41);
      v12 = v16;
      if ( v16 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_68;
        v17 = 56;
        goto LABEL_24;
      }
    }
    else
    {
      if ( BYTE1(v35) != 2 )
      {
        if ( BYTE1(v35) == 3 )
        {
          v12 = -1072875854;
          if ( g_wppLevels )
          {
            v14 = 58;
            goto LABEL_5;
          }
        }
        else
        {
          v12 = -1072875845;
          if ( g_wppLevels )
          {
            v14 = 59;
            goto LABEL_5;
          }
        }
        goto LABEL_68;
      }
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v41);
      v16 = FSVMServerMediaBuffer::Create2DFSVMBuffer(
              (struct IFSVMMediaBufferRelease *)((unsigned __int64)(a1 + 5) & -(__int64)(a1 != 0)),
              (const union FSVMFrameId *)&v35,
              (unsigned __int8 *)(v40 + LODWORD(a1[15 * WORD1(v35) + 21])),
              *((_DWORD *)a1 + 29),
              (const struct FSMediaTypeInfo *)a2,
              a4,
              &GUID_045fa593_8799_42b8_bc8d_8968c6453507,
              &v41);
      v12 = v16;
      if ( v16 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_68;
        v17 = 57;
        goto LABEL_24;
      }
    }
    v18 = ppIMFSample;
    ppIMFSample = 0;
    if ( v18 )
      ((void (__fastcall *)(IMFSample *))v18->lpVtbl->Release)(v18);
    v16 = MFCreateSample(&ppIMFSample);
    v12 = v16;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_68;
      v17 = 60;
      goto LABEL_24;
    }
    v16 = ((__int64 (__fastcall *)(IMFSample *, void *))ppIMFSample->lpVtbl->AddBuffer)(ppIMFSample, v41);
    v12 = v16;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_68;
      v17 = 61;
      goto LABEL_24;
    }
    if ( *((_DWORD *)a1 + 31) )
    {
      ppBuffer = 0;
      ppMFAttributes = 0;
      v36 = 0;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppBuffer);
      v19 = MFCreateMemoryBuffer(*((_DWORD *)a1 + 31), &ppBuffer);
      v12 = v19;
      if ( v19 < 0 )
      {
        if ( !g_wppLevels )
        {
LABEL_38:
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v36);
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppBuffer);
          goto LABEL_68;
        }
        v20 = 62;
LABEL_37:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_f5069778e7c6307a26edc2e496375707_Traceguids, a1, v19);
        goto LABEL_38;
      }
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
      v19 = MFCreateAttributes(&ppMFAttributes, 0);
      v12 = v19;
      if ( v19 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_38;
        v20 = 63;
        goto LABEL_37;
      }
      v21 = ppBuffer;
      QueryInterface = ppBuffer->lpVtbl->QueryInterface;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v36);
      v19 = ((__int64 (__fastcall *)(IMFMediaBuffer *, GUID *, __int64 *))QueryInterface)(
              v21,
              &GUID_00000000_0000_0000_c000_000000000046,
              &v36);
      v12 = v19;
      if ( v19 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_38;
        v20 = 64;
        goto LABEL_37;
      }
      v19 = ((__int64 (__fastcall *)(IMFAttributes *, const GUID *, __int64))ppMFAttributes->lpVtbl->SetUnknown)(
              ppMFAttributes,
              &MF_CAPTURE_METADATA_FRAME_RAWSTREAM,
              v36);
      v12 = v19;
      if ( v19 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_38;
        v20 = 65;
        goto LABEL_37;
      }
      v23 = ppMFAttributes;
      v24 = ppMFAttributes->lpVtbl->QueryInterface;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v36);
      v19 = ((__int64 (__fastcall *)(IMFAttributes *, GUID *, __int64 *))v24)(
              v23,
              &GUID_00000000_0000_0000_c000_000000000046,
              &v36);
      v12 = v19;
      if ( v19 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_38;
        v20 = 66;
        goto LABEL_37;
      }
      v19 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUnknown)(
              ppIMFSample,
              &MFSampleExtension_CaptureMetadata,
              v36);
      v12 = v19;
      if ( v19 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_38;
        v20 = 67;
        goto LABEL_37;
      }
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v36);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppBuffer);
    }
    v16 = ((__int64 (__fastcall *)(IMFSample *, void *, __int64))ppIMFSample->lpVtbl->SetUINT64)(
            ppIMFSample,
            &MFSampleExtension_FSVMQueueConfigFrameIndex,
            v35);
    v12 = v16;
    if ( v16 >= 0 )
    {
      a1[15 * WORD1(v35) + 17] = v35;
      LODWORD(a1[15 * WORD1(v35) + 18]) = 2;
      a1[15 * WORD1(v35) + 25] = 0;
      LODWORD(a1[15 * WORD1(v35) + 26]) = a4;
      v25 = 15LL * WORD1(v35);
      *(_OWORD *)&a1[v25 + 27] = *(_OWORD *)a2;
      *(_OWORD *)&a1[v25 + 29] = *(_OWORD *)(a2 + 16);
      a1[v25 + 31] = *(_QWORD *)(a2 + 32);
      *(_QWORD *)(120LL * WORD1(v35) + v40 + 32) = a1[15 * WORD1(v35) + 17];
      *(_DWORD *)(120LL * WORD1(v35) + v40 + 40) = a1[15 * WORD1(v35) + 18];
      *(_QWORD *)(120LL * WORD1(v35) + v40 + 96) = a1[15 * WORD1(v35) + 25];
      *(_DWORD *)(120LL * WORD1(v35) + v40 + 104) = a1[15 * WORD1(v35) + 26];
      v26 = 15LL * WORD1(v35);
      v27 = v40;
      *(_OWORD *)(v26 * 8 + v40 + 112) = *(_OWORD *)&a1[v26 + 27];
      *(_OWORD *)(v26 * 8 + v27 + 128) = *(_OWORD *)&a1[v26 + 29];
      *(_QWORD *)(v26 * 8 + v27 + 144) = a1[v26 + 31];
      *v13 = ppIMFSample;
      v28 = a1[621];
      ppIMFSample = 0;
      if ( v28 == 10 * (v28 / 10) )
      {
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
        {
          v29 = FSVMTrace::FSVMTrace((FSVMTrace *)v43, (const struct FSVMFrameInfo *)&a1[15 * WORD1(v35) + 17]);
          String = FSString::GetString(v29);
          WPP_SF_qDs(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            69,
            (unsigned int)&WPP_f5069778e7c6307a26edc2e496375707_Traceguids,
            (_DWORD)a1,
            SBYTE2(v35),
            (__int64)String);
          v10 = 1;
        }
        v31 = (v10 & 1) == 0;
      }
      else
      {
        if ( (unsigned __int8)byte_18010EC53 >= 8u )
        {
          v32 = FSVMTrace::FSVMTrace((FSVMTrace *)v43, (const struct FSVMFrameInfo *)&a1[15 * WORD1(v35) + 17]);
          v33 = FSString::GetString(v32);
          WPP_SF_qDs(
            *((_QWORD *)WPP_GLOBAL_Control + 57),
            70,
            (unsigned int)&WPP_f5069778e7c6307a26edc2e496375707_Traceguids,
            (_DWORD)a1,
            SBYTE2(v35),
            (__int64)v33);
          v10 = 2;
        }
        v31 = (v10 & 2) == 0;
      }
      if ( !v31 )
        FSString::~FSString((FSString *)v43);
      ++a1[621];
      goto LABEL_68;
    }
    if ( !g_wppLevels )
      goto LABEL_68;
    v17 = 68;
LABEL_24:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_f5069778e7c6307a26edc2e496375707_Traceguids, a1, v16);
    goto LABEL_68;
  }
  v12 = -1072875850;
  if ( g_wppLevels )
  {
    v14 = 55;
    goto LABEL_5;
  }
LABEL_68:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v42);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v41);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppIMFSample);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800ddc00  push    rbp
0x1800ddc02  push    rbx
0x1800ddc03  push    rsi
0x1800ddc04  push    rdi
0x1800ddc05  push    r12
0x1800ddc07  push    r13
0x1800ddc09  push    r14
0x1800ddc0b  push    r15
0x1800ddc0d  lea     rbp, [rsp-17h]
0x1800ddc12  sub     rsp, 0A8h
0x1800ddc19  xor     r15d, r15d
0x1800ddc1c  mov     r13d, r9d
0x1800ddc1f  mov     [rbp+4Fh+arg_0], r15d
0x1800ddc23  mov     dil, r8b
0x1800ddc26  mov     rax, [rcx]
0x1800ddc29  mov     r12, rdx
0x1800ddc2c  mov     rsi, rcx
0x1800ddc2f  mov     [rbp+4Fh+var_78], r15
0x1800ddc33  mov     r14d, r15d
0x1800ddc36  mov     [rbp+4Fh+arg_0], r15d
0x1800ddc3a  mov     [rbp+4Fh+ppIMFSample], r15
0x1800ddc3e  mov     rax, [rax+38h]
0x1800ddc42  mov     [rbp+4Fh+var_70], r15
0x1800ddc46  mov     [rbp+4Fh+var_68], r15
0x1800ddc4a  mov     [rbp+4Fh+var_A0], r15
0x1800ddc4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddc53  mov     ebx, eax
0x1800ddc55  test    eax, eax
0x1800ddc57  js      loc_1800DE2C1
0x1800ddc5d  mov     r15, [rbp+4Fh+arg_20]
0x1800ddc61  test    r15, r15
0x1800ddc64  jnz     short loc_1800DDC9F
0x1800ddc66  mov     ebx, 80004003h
0x1800ddc6b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ddc72  jb      loc_1800DE2C1
0x1800ddc78  lea     edx, [r15+36h]
0x1800ddc7c  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1800ddc80  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ddc87  lea     r8, WPP_f5069778e7c6307a26edc2e496375707_Traceguids
0x1800ddc8e  mov     r9, rsi
0x1800ddc91  mov     rcx, [rcx+10h]
0x1800ddc95  call    WPP_SF_qD
0x1800ddc9a  jmp     loc_1800DE2C1
0x1800ddc9f  mov     [r15], r14
0x1800ddca2  cmp     [rsi+60h], r14b
0x1800ddca6  jnz     short loc_1800DDCC1
0x1800ddca8  mov     ebx, 0C00D36B6h
0x1800ddcad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ddcb4  jb      loc_1800DE2C1
0x1800ddcba  mov     edx, 37h ; '7'
0x1800ddcbf  jmp     short loc_1800DDC7C
0x1800ddcc1  mov     eax, [r12]
0x1800ddcc5  lea     r9, [rbp+4Fh+arg_0]
0x1800ddcc9  mov     dword ptr [rbp+4Fh+var_A0+4], eax
0x1800ddccc  lea     r8, [rbp+4Fh+var_78]
0x1800ddcd0  mov     rax, [rsi]
0x1800ddcd3  lea     rdx, [rbp+4Fh+var_A0]
0x1800ddcd7  mov     rcx, rsi
0x1800ddcda  mov     byte ptr [rbp+4Fh+var_A0+1], dil
0x1800ddcde  mov     rax, [rax+20h]
0x1800ddce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddce7  xor     edi, edi
0x1800ddce9  mov     ebx, eax
0x1800ddceb  test    eax, eax
0x1800ddced  js      loc_1800DE2C1
0x1800ddcf3  movzx   ecx, byte ptr [rbp+4Fh+var_A0+1]
0x1800ddcf7  sub     ecx, 1
0x1800ddcfa  jz      loc_1800DDDB7
0x1800ddd00  sub     ecx, 1
0x1800ddd03  jz      short loc_1800DDD40
0x1800ddd05  cmp     ecx, 1
0x1800ddd08  jz      short loc_1800DDD24
0x1800ddd0a  mov     ebx, 0C00D36BBh
0x1800ddd0f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ddd16  jb      loc_1800DE2C1
0x1800ddd1c  lea     edx, [rdi+3Bh]
0x1800ddd1f  jmp     loc_1800DDC7C
0x1800ddd24  mov     ebx, 0C00D36B2h
0x1800ddd29  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ddd30  jb      loc_1800DE2C1
0x1800ddd36  mov     edx, 3Ah ; ':'
0x1800ddd3b  jmp     loc_1800DDC7C
0x1800ddd40  lea     rcx, [rbp+4Fh+var_70]
0x1800ddd44  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800ddd49  movzx   eax, word ptr [rbp+4Fh+var_A0+2]
0x1800ddd4d  lea     rdx, [rsi+28h]
0x1800ddd51  mov     r9d, [rsi+74h]; unsigned int
0x1800ddd55  imul    rcx, rax, 78h ; 'x'
0x1800ddd59  mov     rax, rsi
0x1800ddd5c  mov     r8d, [rcx+rsi+0A8h]
0x1800ddd64  add     r8, [rbp+4Fh+var_78]; unsigned __int8 *
0x1800ddd68  neg     rax
0x1800ddd6b  lea     rax, [rbp+4Fh+var_70]
0x1800ddd6f  mov     [rsp+0E0h+var_A8], rax; void **
0x1800ddd74  sbb     rcx, rcx
0x1800ddd77  lea     rax, _GUID_045fa593_8799_42b8_bc8d_8968c6453507
0x1800ddd7e  and     rcx, rdx; struct IFSVMMediaBufferRelease *
0x1800ddd81  mov     [rsp+0E0h+var_B0], rax; struct _GUID *
0x1800ddd86  lea     rdx, [rbp+4Fh+var_A0]; union FSVMFrameId *
0x1800ddd8a  mov     dword ptr [rsp+0E0h+var_B8], r13d; int
0x1800ddd8f  mov     [rsp+0E0h+var_C0], r12; struct FSMediaTypeInfo *
0x1800ddd94  call    ?Create2DFSVMBuffer@FSVMServerMediaBuffer@@SAJPEAUIFSVMMediaBufferRelease@@AEBTFSVMFrameId@@PEAEKAEBUFSMediaTypeInfo@@JAEBU_GUID@@PEAPEAX@Z; FSVMServerMediaBuffer::Create2DFSVMBuffer(IFSVMMediaBufferRelease *,FSVMFrameId const &,uchar *,ulong,FSMediaTypeInfo const &,long,_GUID const &,void * *)
0x1800ddd99  mov     ebx, eax
0x1800ddd9b  test    eax, eax
0x1800ddd9d  jns     loc_1800DDE27
0x1800ddda3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dddaa  jb      loc_1800DE2C1
0x1800dddb0  mov     edx, 39h ; '9'
0x1800dddb5  jmp     short loc_1800DDE1E
0x1800dddb7  lea     rcx, [rbp+4Fh+var_70]
0x1800dddbb  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800dddc0  movzx   eax, word ptr [rbp+4Fh+var_A0+2]
0x1800dddc4  lea     rdx, [rsi+28h]
0x1800dddc8  mov     r9d, [rsi+74h]; unsigned int
0x1800dddcc  imul    rcx, rax, 78h ; 'x'
0x1800dddd0  mov     rax, rsi
0x1800dddd3  mov     r8d, [rcx+rsi+0A8h]
0x1800ddddb  add     r8, [rbp+4Fh+var_78]; unsigned __int8 *
0x1800ddddf  neg     rax
0x1800ddde2  lea     rax, [rbp+4Fh+var_70]
0x1800ddde6  mov     [rsp+0E0h+var_B8], rax; void **
0x1800dddeb  sbb     rcx, rcx
0x1800dddee  and     rcx, rdx; struct IFSVMMediaBufferRelease *
0x1800dddf1  lea     rax, _GUID_045fa593_8799_42b8_bc8d_8968c6453507
0x1800dddf8  lea     rdx, [rbp+4Fh+var_A0]; union FSVMFrameId *
0x1800dddfc  mov     [rsp+0E0h+var_C0], rax; struct _GUID *
0x1800dde01  call    ?Create1DFSVMBuffer@FSVMServerMediaBuffer@@SAJPEAUIFSVMMediaBufferRelease@@AEBTFSVMFrameId@@PEAEKAEBU_GUID@@PEAPEAX@Z; FSVMServerMediaBuffer::Create1DFSVMBuffer(IFSVMMediaBufferRelease *,FSVMFrameId const &,uchar *,ulong,_GUID const &,void * *)
0x1800dde06  mov     ebx, eax
0x1800dde08  test    eax, eax
0x1800dde0a  jns     short loc_1800DDE27
0x1800dde0c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dde13  jb      loc_1800DE2C1
0x1800dde19  mov     edx, 38h ; '8'
0x1800dde1e  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800dde22  jmp     loc_1800DDC80
0x1800dde27  mov     rcx, [rbp+4Fh+ppIMFSample]
0x1800dde2b  mov     [rbp+4Fh+ppIMFSample], rdi
0x1800dde2f  test    rcx, rcx
0x1800dde32  jz      short loc_1800DDE40
0x1800dde34  mov     rax, [rcx]
0x1800dde37  mov     rax, [rax+10h]
0x1800dde3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dde40  lea     rcx, [rbp+4Fh+ppIMFSample]; ppIMFSample
0x1800dde44  call    cs:__imp_MFCreateSample
0x1800dde4a  mov     ebx, eax
0x1800dde4c  test    eax, eax
0x1800dde4e  jns     short loc_1800DDE64
0x1800dde50  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dde57  jb      loc_1800DE2C1
0x1800dde5d  mov     edx, 3Ch ; '<'
0x1800dde62  jmp     short loc_1800DDE1E
0x1800dde64  mov     rcx, [rbp+4Fh+ppIMFSample]
0x1800dde68  mov     rdx, [rbp+4Fh+var_70]
0x1800dde6c  mov     rax, [rcx]
0x1800dde6f  mov     rax, [rax+150h]
0x1800dde76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dde7b  mov     ebx, eax
0x1800dde7d  test    eax, eax
0x1800dde7f  jns     short loc_1800DDE95
0x1800dde81  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dde88  jb      loc_1800DE2C1
0x1800dde8e  mov     edx, 3Dh ; '='
0x1800dde93  jmp     short loc_1800DDE1E
0x1800dde95  cmp     [rsi+7Ch], edi
0x1800dde98  jbe     loc_1800DE05A
0x1800dde9e  lea     rcx, [rbp+4Fh+ppBuffer]
0x1800ddea2  mov     [rbp+4Fh+ppBuffer], rdi
0x1800ddea6  mov     [rbp+4Fh+ppMFAttributes], rdi
0x1800ddeaa  mov     [rbp+4Fh+var_98], rdi
0x1800ddeae  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800ddeb3  mov     ecx, [rsi+7Ch]; cbMaxLength
0x1800ddeb6  lea     rdx, [rbp+4Fh+ppBuffer]; ppBuffer
0x1800ddeba  call    cs:__imp_MFCreateMemoryBuffer
0x1800ddec0  mov     ebx, eax
0x1800ddec2  test    eax, eax
0x1800ddec4  jns     short loc_1800DDF12
0x1800ddec6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ddecd  jb      short loc_1800DDEF2
0x1800ddecf  mov     edx, 3Eh ; '>'
0x1800dded4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ddedb  lea     r8, WPP_f5069778e7c6307a26edc2e496375707_Traceguids
0x1800ddee2  mov     r9, rsi
0x1800ddee5  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800ddee9  mov     rcx, [rcx+10h]
0x1800ddeed  call    WPP_SF_qD
0x1800ddef2  lea     rcx, [rbp+4Fh+var_98]; void *
0x1800ddef6  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800ddefb  lea     rcx, [rbp+4Fh+ppMFAttributes]; void *
0x1800ddeff  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800ddf04  lea     rcx, [rbp+4Fh+ppBuffer]; void *
0x1800ddf08  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800ddf0d  jmp     loc_1800DE2C1
0x1800ddf12  lea     rcx, [rbp+4Fh+ppMFAttributes]
0x1800ddf16  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800ddf1b  xor     edx, edx; cInitialSize
0x1800ddf1d  lea     rcx, [rbp+4Fh+ppMFAttributes]; ppMFAttributes
0x1800ddf21  call    cs:__imp_MFCreateAttributes
0x1800ddf27  mov     ebx, eax
0x1800ddf29  test    eax, eax
0x1800ddf2b  jns     short loc_1800DDF3D
0x1800ddf2d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ddf34  jb      short loc_1800DDEF2
0x1800ddf36  mov     edx, 3Fh ; '?'
0x1800ddf3b  jmp     short loc_1800DDED4
0x1800ddf3d  mov     rdi, [rbp+4Fh+ppBuffer]
0x1800ddf41  lea     rcx, [rbp+4Fh+var_98]
0x1800ddf45  mov     rax, [rdi]
0x1800ddf48  mov     rbx, [rax]
0x1800ddf4b  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800ddf50  lea     r8, [rbp+4Fh+var_98]
0x1800ddf54  mov     rcx, rdi
0x1800ddf57  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800ddf5e  mov     rax, rbx
0x1800ddf61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddf66  mov     ebx, eax
0x1800ddf68  test    eax, eax
0x1800ddf6a  jns     short loc_1800DDF83
0x1800ddf6c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ddf73  jb      loc_1800DDEF2
0x1800ddf79  mov     edx, 40h ; '@'
0x1800ddf7e  jmp     loc_1800DDED4
0x1800ddf83  mov     rcx, [rbp+4Fh+ppMFAttributes]
0x1800ddf87  lea     rdx, MF_CAPTURE_METADATA_FRAME_RAWSTREAM
0x1800ddf8e  mov     r8, [rbp+4Fh+var_98]
0x1800ddf92  mov     rax, [rcx]
0x1800ddf95  mov     rax, [rax+0D8h]
0x1800ddf9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddfa1  mov     ebx, eax
0x1800ddfa3  test    eax, eax
0x1800ddfa5  jns     short loc_1800DDFBE
0x1800ddfa7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ddfae  jb      loc_1800DDEF2
0x1800ddfb4  mov     edx, 41h ; 'A'
0x1800ddfb9  jmp     loc_1800DDED4
0x1800ddfbe  mov     rdi, [rbp+4Fh+ppMFAttributes]
0x1800ddfc2  lea     rcx, [rbp+4Fh+var_98]
0x1800ddfc6  mov     rax, [rdi]
0x1800ddfc9  mov     rbx, [rax]
0x1800ddfcc  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800ddfd1  lea     r8, [rbp+4Fh+var_98]
0x1800ddfd5  mov     rcx, rdi
0x1800ddfd8  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800ddfdf  mov     rax, rbx
0x1800ddfe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddfe7  xor     edi, edi
0x1800ddfe9  mov     ebx, eax
0x1800ddfeb  test    eax, eax
0x1800ddfed  jns     short loc_1800DE004
0x1800ddfef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ddff6  jb      loc_1800DDEF2
0x1800ddffc  lea     edx, [rdi+42h]
0x1800ddfff  jmp     loc_1800DDED4
0x1800de004  mov     rcx, [rbp+4Fh+ppIMFSample]
0x1800de008  lea     rdx, MFSampleExtension_CaptureMetadata
0x1800de00f  mov     r8, [rbp+4Fh+var_98]
0x1800de013  mov     rax, [rcx]
0x1800de016  mov     rax, [rax+0D8h]
0x1800de01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de022  mov     ebx, eax
0x1800de024  test    eax, eax
0x1800de026  jns     short loc_1800DE03F
0x1800de028  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800de02f  jb      loc_1800DDEF2
0x1800de035  mov     edx, 43h ; 'C'
0x1800de03a  jmp     loc_1800DDED4
0x1800de03f  lea     rcx, [rbp+4Fh+var_98]; void *
0x1800de043  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800de048  lea     rcx, [rbp+4Fh+ppMFAttributes]; void *
0x1800de04c  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800de051  lea     rcx, [rbp+4Fh+ppBuffer]; void *
0x1800de055  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800de05a  mov     rcx, [rbp+4Fh+ppIMFSample]
0x1800de05e  lea     rdx, MFSampleExtension_FSVMQueueConfigFrameIndex
0x1800de065  mov     r8, [rbp+4Fh+var_A0]
0x1800de069  mov     rax, [rcx]
0x1800de06c  mov     rax, [rax+0B0h]
0x1800de073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de078  mov     ebx, eax
0x1800de07a  test    eax, eax
0x1800de07c  jns     short loc_1800DE095
0x1800de07e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800de085  jb      loc_1800DE2C1
0x1800de08b  mov     edx, 44h ; 'D'
0x1800de090  jmp     loc_1800DDE1E
0x1800de095  movzx   eax, word ptr [rbp+4Fh+var_A0+2]
0x1800de099  imul    rcx, rax, 78h ; 'x'
0x1800de09d  mov     rax, [rbp+4Fh+var_A0]
0x1800de0a1  mov     [rcx+rsi+88h], rax
0x1800de0a9  movzx   eax, word ptr [rbp+4Fh+var_A0+2]
0x1800de0ad  imul    rcx, rax, 78h ; 'x'
0x1800de0b1  mov     dword ptr [rcx+rsi+90h], 2
0x1800de0bc  movzx   eax, word ptr [rbp+4Fh+var_A0+2]
0x1800de0c0  imul    rcx, rax, 78h ; 'x'
0x1800de0c4  mov     [rcx+rsi+0C8h], rdi
0x1800de0cc  movzx   eax, word ptr [rbp+4Fh+var_A0+2]
0x1800de0d0  imul    rcx, rax, 78h ; 'x'
0x1800de0d4  mov     [rcx+rsi+0D0h], r13d
0x1800de0dc  movzx   eax, word ptr [rbp+4Fh+var_A0+2]
0x1800de0e0  movups  xmm0, xmmword ptr [r12]
0x1800de0e5  imul    rcx, rax, 78h ; 'x'
  ... truncated ...
```
