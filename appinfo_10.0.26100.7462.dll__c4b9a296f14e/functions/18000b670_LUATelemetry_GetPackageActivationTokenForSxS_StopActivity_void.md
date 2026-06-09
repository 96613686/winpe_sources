# LUATelemetry::GetPackageActivationTokenForSxS::StopActivity(void)

- ea: `0x18000b670`
- end: `0x18000bb05`
- name: `?StopActivity@GetPackageActivationTokenForSxS@LUATelemetry@@MEAAXXZ`
- size: `1173`
- prototype: `void __fastcall(LUATelemetry::GetPackageActivationTokenForSxS *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x18000b670`
- `0x18000cb30`
- `0x180010f8c`
- `0x180018d70`
- `0x180018da8`
- `0x180018dcc`
- `0x18001fd6c`
- `0x180033cdc`
- `0x180033ecc`
- `0x180044a20`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ba45`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ba45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba86`

## pseudocode

```c
void __fastcall LUATelemetry::GetPackageActivationTokenForSxS::StopActivity(
        LUATelemetry::GetPackageActivationTokenForSxS *this)
{
  __int64 FailureInfo; // rbx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  const unsigned __int16 *v7; // rdi
  const wchar_t *v8; // rsi
  const unsigned __int16 *v9; // r15
  const unsigned __int16 *v10; // r12
  __int64 v11; // rax
  const wchar_t *v12; // r8
  const unsigned __int16 *v13; // r9
  const wchar_t *v14; // r10
  const unsigned __int16 *v15; // r11
  __int64 v16; // rcx
  const GUID *v17; // rbx
  __int64 v18; // rdx
  bool v19; // zf
  int v20; // edx
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  int v33; // ecx
  const struct _tlgProvider_t *v34; // rcx
  const struct _tlgProvider_t *v35; // rax
  int v36; // ebx
  __int64 v37; // rcx
  int v38; // eax
  int v39; // r9d
  int Result; // [rsp+40h] [rbp-C0h] BYREF
  const struct _tlgProvider_t *v41; // [rsp+48h] [rbp-B8h] BYREF
  int v42; // [rsp+50h] [rbp-B0h] BYREF
  int v43; // [rsp+54h] [rbp-ACh] BYREF
  int v44; // [rsp+58h] [rbp-A8h] BYREF
  int v45; // [rsp+5Ch] [rbp-A4h] BYREF
  int v46; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v47; // [rsp+68h] [rbp-98h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-70h] BYREF
  void *v51; // [rsp+A0h] [rbp-60h]
  int v52; // [rsp+A8h] [rbp-58h]
  int v53; // [rsp+ACh] [rbp-54h]
  __int64 *v54; // [rsp+B0h] [rbp-50h]
  __int64 v55; // [rsp+B8h] [rbp-48h]
  __int64 *v56; // [rsp+C0h] [rbp-40h]
  __int64 v57; // [rsp+C8h] [rbp-38h]
  int *v58; // [rsp+D0h] [rbp-30h]
  __int64 v59; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v60; // [rsp+E0h] [rbp-20h]
  int v61; // [rsp+E8h] [rbp-18h]
  int v62; // [rsp+ECh] [rbp-14h]
  int *v63; // [rsp+F0h] [rbp-10h]
  __int64 v64; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v65; // [rsp+100h] [rbp+0h]
  int v66; // [rsp+108h] [rbp+8h]
  int v67; // [rsp+10Ch] [rbp+Ch]
  int *v68; // [rsp+110h] [rbp+10h]
  __int64 v69; // [rsp+118h] [rbp+18h]
  const wchar_t *v70; // [rsp+120h] [rbp+20h]
  int v71; // [rsp+128h] [rbp+28h]
  int v72; // [rsp+12Ch] [rbp+2Ch]
  int *v73; // [rsp+130h] [rbp+30h]
  __int64 v74; // [rsp+138h] [rbp+38h]
  const unsigned __int16 *v75; // [rsp+140h] [rbp+40h]
  int v76; // [rsp+148h] [rbp+48h]
  int v77; // [rsp+14Ch] [rbp+4Ch]
  int *v78; // [rsp+150h] [rbp+50h]
  __int64 v79; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v80; // [rsp+160h] [rbp+60h]
  int v81; // [rsp+168h] [rbp+68h]
  int v82; // [rsp+16Ch] [rbp+6Ch]
  const wchar_t *v83; // [rsp+170h] [rbp+70h]
  int v84; // [rsp+178h] [rbp+78h]
  int v85; // [rsp+17Ch] [rbp+7Ch]
  int *v86; // [rsp+180h] [rbp+80h]
  __int64 v87; // [rsp+188h] [rbp+88h]
  const unsigned __int16 *v88; // [rsp+190h] [rbp+90h]
  int v89; // [rsp+198h] [rbp+98h]
  int v90; // [rsp+19Ch] [rbp+9Ch]
  const wchar_t *v91; // [rsp+1A0h] [rbp+A0h]
  int v92; // [rsp+1A8h] [rbp+A8h]
  int v93; // [rsp+1ACh] [rbp+ACh]

  FailureInfo = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo();
  if ( FailureInfo )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v3 = LUATelemetry::Provider();
    v41 = v3;
    if ( *(_DWORD *)v3 > 5u )
    {
      v5 = 0x200000000000LL;
      if ( (*((_QWORD *)v3 + 2) & 0x200000000000LL) != 0
        && (*((_QWORD *)v3 + 3) & 0x200000000000LL) == *((_QWORD *)v3 + 3) )
      {
        v7 = *(const unsigned __int16 **)(FailureInfo + 72);
        v8 = *(const wchar_t **)(FailureInfo + 24);
        v9 = *(const unsigned __int16 **)(FailureInfo + 128);
        v10 = *(const unsigned __int16 **)(FailureInfo + 56);
        v42 = *(_DWORD *)(FailureInfo + 104);
        v43 = *(_DWORD *)(FailureInfo + 80);
        v44 = *(_DWORD *)(FailureInfo + 32);
        v45 = *(_DWORD *)FailureInfo;
        v46 = *(_DWORD *)(FailureInfo + 64);
        Result = *(_DWORD *)(FailureInfo + 8);
        v48 = 0x1000000;
        v47 = 0;
        v11 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(this);
        v16 = -1;
        v17 = (const GUID *)v11;
        if ( v12 )
        {
          v18 = -1;
          do
            v19 = v12[++v18] == 0;
          while ( !v19 );
          v20 = 2 * v18 + 2;
        }
        else
        {
          v12 = &String2;
          v20 = 2;
        }
        v91 = v12;
        v92 = v20;
        v93 = 0;
        if ( v13 )
        {
          v21 = -1;
          do
            ++v21;
          while ( *((_BYTE *)v13 + v21) );
          v22 = v21 + 1;
        }
        else
        {
          v13 = &word_18004B3E8;
          v22 = 1;
        }
        v89 = v22;
        v86 = &v42;
        v88 = v13;
        v90 = 0;
        v87 = 4;
        if ( v14 )
        {
          v23 = -1;
          do
            v19 = v14[++v23] == 0;
          while ( !v19 );
          v24 = 2 * v23 + 2;
        }
        else
        {
          v14 = &String2;
          v24 = 2;
        }
        v83 = v14;
        v84 = v24;
        v85 = 0;
        if ( v15 )
        {
          v25 = -1;
          do
            ++v25;
          while ( *((_BYTE *)v15 + v25) );
          v26 = v25 + 1;
        }
        else
        {
          v15 = &word_18004B3E8;
          v26 = 1;
        }
        v81 = v26;
        v78 = &v43;
        v80 = v15;
        v82 = 0;
        v79 = 4;
        if ( v7 )
        {
          v27 = -1;
          do
            ++v27;
          while ( *((_BYTE *)v7 + v27) );
          v28 = v27 + 1;
        }
        else
        {
          v7 = &word_18004B3E8;
          v28 = 1;
        }
        v76 = v28;
        v75 = v7;
        v73 = &v44;
        v77 = 0;
        v74 = 4;
        if ( v8 )
        {
          v29 = -1;
          do
            v19 = v8[++v29] == 0;
          while ( !v19 );
          v30 = 2 * v29 + 2;
        }
        else
        {
          v8 = &String2;
          v30 = 2;
        }
        v71 = v30;
        v70 = v8;
        v68 = &v45;
        v72 = 0;
        v69 = 4;
        if ( v9 )
        {
          v31 = -1;
          do
            ++v31;
          while ( *((_BYTE *)v9 + v31) );
          v32 = v31 + 1;
        }
        else
        {
          v9 = &word_18004B3E8;
          v32 = 1;
        }
        v66 = v32;
        v65 = v9;
        v63 = &v46;
        v67 = 0;
        v64 = 4;
        if ( v10 )
        {
          do
            ++v16;
          while ( *((_BYTE *)v10 + v16) );
          v33 = v16 + 1;
        }
        else
        {
          v10 = &word_18004B3E8;
          v33 = 1;
        }
        v61 = v33;
        v34 = v41;
        v58 = &Result;
        v60 = v10;
        v56 = &v48;
        v62 = 0;
        v54 = &v47;
        *(_DWORD *)&EventDescriptor.Level = 517;
        EventDescriptor.Keyword = 0x200000000000LL;
        UserData.Ptr = *((_QWORD *)v41 + 1);
        v59 = 4;
        v57 = 8;
        v55 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        v51 = &unk_1800535F9;
        UserData.Reserved = 2;
        v52 = 299;
        v53 = 1;
        LODWORD(v41) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(*((_QWORD *)v34 + 4), &EventDescriptor, v17, 0, 0x12u, &UserData);
      }
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v35 = LUATelemetry::Provider();
    v36 = (int)v35;
    if ( *(_DWORD *)v35 > 5u && (unsigned __int8)tlgKeywordOn(v35, 0x200000000000LL) )
    {
      LODWORD(v41) = GetCurrentThreadId();
      Result = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(this);
      v47 = 0;
      v38 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(v37);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v36,
        (unsigned int)&unk_18005272A,
        v38,
        v39,
        (__int64)&v47,
        (__int64)&Result,
        (__int64)&v41);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v4,
    v5,
    v6);
}

```

## disassembly

```asm
0x18000b670  push    rbp
0x18000b672  push    rbx
0x18000b673  push    r13
0x18000b675  push    r14
0x18000b677  lea     rbp, [rsp-0C8h]
0x18000b67f  sub     rsp, 1C8h
0x18000b686  mov     rax, cs:__security_cookie
0x18000b68d  xor     rax, rsp
0x18000b690  mov     [rbp+0E0h+var_30], rax
0x18000b697  mov     r14, rcx
0x18000b69a  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x18000b69f  mov     rbx, rax
0x18000b6a2  mov     rcx, r14
0x18000b6a5  test    rax, rax
0x18000b6a8  jz      loc_18000BA5E
0x18000b6ae  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000b6b3  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000b6b8  mov     [rsp+1E0h+var_198], rax
0x18000b6bd  cmp     dword ptr [rax], 5
0x18000b6c0  jbe     loc_18000BADF
0x18000b6c6  mov     r8, 200000000000h
0x18000b6d0  test    [rax+10h], r8
0x18000b6d4  jz      loc_18000BADF
0x18000b6da  mov     rcx, [rax+18h]
0x18000b6de  and     rcx, r8
0x18000b6e1  cmp     rcx, [rax+18h]
0x18000b6e5  jnz     loc_18000BADF
0x18000b6eb  mov     [rsp+1E0h+arg_8], rsi
0x18000b6f3  mov     [rsp+1E0h+arg_10], rdi
0x18000b6fb  mov     [rsp+1E0h+arg_18], r12
0x18000b703  mov     [rsp+1E0h+var_20], r15
0x18000b70b  mov     eax, [rbx+68h]
0x18000b70e  xor     r13d, r13d
0x18000b711  mov     r8, [rbx+78h]
0x18000b715  mov     rcx, r14
0x18000b718  mov     r9, [rbx+70h]
0x18000b71c  mov     r10, [rbx+60h]
0x18000b720  mov     r11, [rbx+58h]
0x18000b724  mov     rdi, [rbx+48h]
0x18000b728  mov     rsi, [rbx+18h]
0x18000b72c  mov     r15, [rbx+80h]
0x18000b733  mov     r12, [rbx+38h]
0x18000b737  mov     [rsp+1E0h+var_190], eax
0x18000b73b  mov     eax, [rbx+50h]
0x18000b73e  mov     [rsp+1E0h+var_18C], eax
0x18000b742  mov     eax, [rbx+20h]
0x18000b745  mov     [rsp+1E0h+var_188], eax
0x18000b749  mov     eax, [rbx]
0x18000b74b  mov     [rsp+1E0h+var_184], eax
0x18000b74f  mov     eax, [rbx+40h]
0x18000b752  mov     [rsp+1E0h+var_180], eax
0x18000b756  mov     eax, [rbx+8]
0x18000b759  mov     [rsp+1E0h+var_1A0], eax
0x18000b75d  mov     [rsp+1E0h+var_170], 1000000h
0x18000b766  mov     [rsp+1E0h+var_178], r13
0x18000b76b  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000b770  lea     rcx, [r13-1]
0x18000b774  mov     rbx, rax
0x18000b777  test    r8, r8
0x18000b77a  jz      short loc_18000B795
0x18000b77c  mov     rdx, rcx
0x18000b77f  nop
0x18000b780  cmp     [r8+rdx*2+2], r13w
0x18000b786  lea     rdx, [rdx+1]
0x18000b78a  jnz     short loc_18000B780
0x18000b78c  lea     edx, ds:2[rdx*2]
0x18000b793  jmp     short loc_18000B7A1
0x18000b795  lea     r8, String2
0x18000b79c  mov     edx, 2
0x18000b7a1  mov     [rbp+0E0h+var_40], r8
0x18000b7a8  mov     [rbp+0E0h+var_38], edx
0x18000b7ae  mov     [rbp+0E0h+var_34], r13d
0x18000b7b5  test    r9, r9
0x18000b7b8  jz      short loc_18000B7CD
0x18000b7ba  mov     rax, rcx
0x18000b7bd  nop     dword ptr [rax]
0x18000b7c0  inc     rax
0x18000b7c3  cmp     [r9+rax], r13b
0x18000b7c7  jnz     short loc_18000B7C0
0x18000b7c9  inc     eax
0x18000b7cb  jmp     short loc_18000B7D9
0x18000b7cd  lea     r9, word_18004B3E8
0x18000b7d4  mov     eax, 1
0x18000b7d9  mov     [rbp+0E0h+var_48], eax
0x18000b7df  lea     rax, [rsp+1E0h+var_190]
0x18000b7e4  mov     [rbp+0E0h+var_60], rax
0x18000b7eb  mov     [rbp+0E0h+var_50], r9
0x18000b7f2  mov     [rbp+0E0h+var_44], r13d
0x18000b7f9  mov     [rbp+0E0h+var_58], 4
0x18000b804  test    r10, r10
0x18000b807  jz      short loc_18000B825
0x18000b809  mov     rax, rcx
0x18000b80c  nop     dword ptr [rax+00h]
0x18000b810  cmp     [r10+rax*2+2], r13w
0x18000b816  lea     rax, [rax+1]
0x18000b81a  jnz     short loc_18000B810
0x18000b81c  lea     eax, ds:2[rax*2]
0x18000b823  jmp     short loc_18000B831
0x18000b825  lea     r10, String2
0x18000b82c  mov     eax, 2
0x18000b831  mov     [rbp+0E0h+var_70], r10
0x18000b835  mov     [rbp+0E0h+var_68], eax
0x18000b838  mov     [rbp+0E0h+var_64], r13d
0x18000b83c  test    r11, r11
0x18000b83f  jz      short loc_18000B851
0x18000b841  mov     rax, rcx
0x18000b844  inc     rax
0x18000b847  cmp     [r11+rax], r13b
0x18000b84b  jnz     short loc_18000B844
0x18000b84d  inc     eax
0x18000b84f  jmp     short loc_18000B85D
0x18000b851  lea     r11, word_18004B3E8
0x18000b858  mov     eax, 1
0x18000b85d  mov     [rbp+0E0h+var_78], eax
0x18000b860  lea     rax, [rsp+1E0h+var_18C]
0x18000b865  mov     [rbp+0E0h+var_90], rax
0x18000b869  mov     [rbp+0E0h+var_80], r11
0x18000b86d  mov     [rbp+0E0h+var_74], r13d
0x18000b871  mov     [rbp+0E0h+var_88], 4
0x18000b879  test    rdi, rdi
0x18000b87c  jz      short loc_18000B88E
0x18000b87e  mov     rax, rcx
0x18000b881  inc     rax
0x18000b884  cmp     [rdi+rax], r13b
0x18000b888  jnz     short loc_18000B881
0x18000b88a  inc     eax
0x18000b88c  jmp     short loc_18000B89A
0x18000b88e  lea     rdi, word_18004B3E8
0x18000b895  mov     eax, 1
0x18000b89a  mov     [rbp+0E0h+var_98], eax
0x18000b89d  lea     rax, [rsp+1E0h+var_188]
0x18000b8a2  mov     [rbp+0E0h+var_A0], rdi
0x18000b8a6  mov     rdi, [rsp+1E0h+arg_10]
0x18000b8ae  mov     [rbp+0E0h+var_B0], rax
0x18000b8b2  mov     [rbp+0E0h+var_94], r13d
0x18000b8b6  mov     [rbp+0E0h+var_A8], 4
0x18000b8be  test    rsi, rsi
0x18000b8c1  jz      short loc_18000B8E5
0x18000b8c3  mov     rax, rcx
0x18000b8c6  nop     word ptr [rax+rax+00000000h]
0x18000b8d0  cmp     [rsi+rax*2+2], r13w
0x18000b8d6  lea     rax, [rax+1]
0x18000b8da  jnz     short loc_18000B8D0
0x18000b8dc  lea     eax, ds:2[rax*2]
0x18000b8e3  jmp     short loc_18000B8F1
0x18000b8e5  lea     rsi, String2
0x18000b8ec  mov     eax, 2
0x18000b8f1  mov     [rbp+0E0h+var_B8], eax
0x18000b8f4  lea     rax, [rsp+1E0h+var_184]
0x18000b8f9  mov     [rbp+0E0h+var_C0], rsi
0x18000b8fd  mov     rsi, [rsp+1E0h+arg_8]
0x18000b905  mov     [rbp+0E0h+var_D0], rax
0x18000b909  mov     [rbp+0E0h+var_B4], r13d
0x18000b90d  mov     [rbp+0E0h+var_C8], 4
0x18000b915  test    r15, r15
0x18000b918  jz      short loc_18000B92D
0x18000b91a  mov     rax, rcx
0x18000b91d  nop     dword ptr [rax]
0x18000b920  inc     rax
0x18000b923  cmp     [r15+rax], r13b
0x18000b927  jnz     short loc_18000B920
0x18000b929  inc     eax
0x18000b92b  jmp     short loc_18000B939
0x18000b92d  lea     r15, word_18004B3E8
0x18000b934  mov     eax, 1
0x18000b939  mov     [rbp+0E0h+var_D8], eax
0x18000b93c  lea     rax, [rsp+1E0h+var_180]
0x18000b941  mov     [rbp+0E0h+var_E0], r15
0x18000b945  mov     r15, [rsp+1E0h+var_20]
0x18000b94d  mov     [rbp+0E0h+var_F0], rax
0x18000b951  mov     [rbp+0E0h+var_D4], r13d
0x18000b955  mov     [rbp+0E0h+var_E8], 4
0x18000b95d  test    r12, r12
0x18000b960  jz      short loc_18000B96F
0x18000b962  inc     rcx
0x18000b965  cmp     [r12+rcx], r13b
0x18000b969  jnz     short loc_18000B962
0x18000b96b  inc     ecx
0x18000b96d  jmp     short loc_18000B97B
0x18000b96f  lea     r12, word_18004B3E8
0x18000b976  mov     ecx, 1
0x18000b97b  mov     [rbp+0E0h+var_F8], ecx
0x18000b97e  lea     rax, [rsp+1E0h+var_1A0]
0x18000b983  mov     rcx, [rsp+1E0h+var_198]
0x18000b988  lea     rdx, _TraceLoggingMetadata
0x18000b98f  mov     [rbp+0E0h+var_110], rax
0x18000b993  xor     r9d, r9d; RelatedActivityId
0x18000b996  mov     [rbp+0E0h+var_100], r12
0x18000b99a  lea     rax, [rsp+1E0h+var_170]
0x18000b99f  mov     [rbp+0E0h+var_120], rax
0x18000b9a3  mov     r8, rbx; ActivityId
0x18000b9a6  lea     rax, [rsp+1E0h+var_178]
0x18000b9ab  mov     [rbp+0E0h+var_F4], r13d
0x18000b9af  mov     [rbp+0E0h+var_130], rax
0x18000b9b3  movzx   eax, cs:word_1800535EF
0x18000b9ba  mov     dword ptr [rsp+1E0h+EventDescriptor.Level], eax
0x18000b9be  mov     rax, 200000000000h
0x18000b9c8  mov     [rbp+0E0h+EventDescriptor.Keyword], rax
0x18000b9cc  mov     rax, [rcx+8]
0x18000b9d0  mov     [rbp+0E0h+var_150.Ptr], rax
0x18000b9d4  mov     [rbp+0E0h+var_108], 4
0x18000b9dc  mov     [rbp+0E0h+var_118], 8
0x18000b9e4  mov     [rbp+0E0h+var_128], 8
0x18000b9ec  mov     dword ptr [rsp+1E0h+EventDescriptor.Id], 0B000000h
0x18000b9f4  movzx   eax, word ptr [rax]
0x18000b9f7  mov     [rbp+0E0h+var_150.Size], eax
0x18000b9fa  lea     rax, unk_1800535F9
0x18000ba01  mov     [rbp+0E0h+var_140], rax
0x18000ba05  lea     rax, _TraceLoggingMetadataEnd
0x18000ba0c  sub     eax, edx
0x18000ba0e  mov     dword ptr [rbp+0E0h+var_150.0Ch], 2
0x18000ba15  mov     [rbp+0E0h+var_138], 12Bh
0x18000ba1c  lea     rdx, [rsp+1E0h+EventDescriptor]; EventDescriptor
0x18000ba21  mov     [rbp+0E0h+var_134], 1
0x18000ba28  mov     dword ptr [rsp+1E0h+var_198], eax
0x18000ba2c  mov     eax, dword ptr [rsp+1E0h+var_198]
0x18000ba30  mov     rcx, [rcx+20h]; RegHandle
0x18000ba34  lea     rax, [rbp+0E0h+var_150]
0x18000ba38  mov     [rsp+1E0h+UserData], rax; UserData
0x18000ba3d  mov     [rsp+1E0h+UserDataCount], 12h; UserDataCount
0x18000ba45  call    cs:__imp_EventWriteTransfer
0x18000ba4c  nop     dword ptr [rax+rax+00h]
0x18000ba51  mov     r12, [rsp+1E0h+arg_18]
0x18000ba59  jmp     loc_18000BADF
0x18000ba5e  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000ba63  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000ba68  mov     rbx, rax
0x18000ba6b  cmp     dword ptr [rax], 5
0x18000ba6e  jbe     short loc_18000BADF
0x18000ba70  mov     rdx, 200000000000h
0x18000ba7a  mov     rcx, rax
0x18000ba7d  call    _tlgKeywordOn
0x18000ba82  test    al, al
0x18000ba84  jz      short loc_18000BADF
0x18000ba86  call    cs:__imp_GetCurrentThreadId
0x18000ba8d  nop     dword ptr [rax+rax+00h]
0x18000ba92  mov     rcx, r14
0x18000ba95  mov     dword ptr [rsp+1E0h+var_198], eax
0x18000ba99  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x18000ba9e  xor     r13d, r13d
0x18000baa1  mov     [rsp+1E0h+var_1A0], eax
0x18000baa5  mov     [rsp+1E0h+var_178], r13
0x18000baaa  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000baaf  lea     rcx, [rsp+1E0h+var_198]
0x18000bab4  mov     r8, rax
0x18000bab7  mov     [rsp+1E0h+var_1B0], rcx
0x18000babc  lea     rdx, unk_18005272A
0x18000bac3  lea     rcx, [rsp+1E0h+var_1A0]
0x18000bac8  mov     [rsp+1E0h+UserData], rcx
0x18000bacd  lea     rcx, [rsp+1E0h+var_178]
0x18000bad2  mov     qword ptr [rsp+1E0h+UserDataCount], rcx
0x18000bad7  mov     rcx, rbx
0x18000bada  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000badf  mov     rcx, r14
0x18000bae2  call    ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000bae7  mov     rcx, [rbp+0E0h+var_30]
0x18000baee  xor     rcx, rsp; StackCookie
0x18000baf1  call    __security_check_cookie
0x18000baf6  add     rsp, 1C8h
0x18000bafd  pop     r14
0x18000baff  pop     r13
0x18000bb01  pop     rbx
0x18000bb02  pop     rbp
0x18000bb03  retn
```
