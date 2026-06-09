# SDKCreatePassThroughProcessor(HSTRING__ *,void const *,unsigned __int64,IZnPassThroughProcessor * *)

- ea: `0x18000b210`
- end: `0x18000ba1a`
- name: `?SDKCreatePassThroughProcessor@@YAJPEAUHSTRING__@@PEBX_KPEAPEAVIZnPassThroughProcessor@@@Z`
- size: `2058`
- prototype: `__int64 __fastcall(HSTRING string, const void *, unsigned __int64, struct IZnPassThroughProcessor **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x180003f80`

## callees

- `0x1800031a4`
- `0x180003580`
- `0x18000358c`
- `0x18000a8a0`
- `0x18000aa20`
- `0x18000ac20`
- `0x18000b210`
- `0x18000e4f0`
- `0x1800132a0`
- `0x180015f30`
- `0x180017240`
- `0x1800a031b`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000b380`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000b5d5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000b380`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000b5d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall SDKCreatePassThroughProcessor(
        HSTRING string,
        const void *a2,
        __int64 a3,
        struct IZnPassThroughProcessor **a4)
{
  SDK::LogicalFunction *v5; // rax
  __int64 v6; // rsi
  volatile signed __int32 *v7; // rax
  volatile signed __int32 *v8; // rbx
  SDK::Unit::BooleanDevice *v9; // rax
  SDK::Unit::BooleanDevice *v10; // r14
  volatile signed __int32 *v11; // rax
  volatile signed __int32 *v12; // rdi
  unsigned int v13; // r12d
  const WCHAR *StringRawBuffer_0; // r12
  volatile signed __int32 *v15; // rax
  _QWORD *v16; // r13
  volatile signed __int32 *v17; // rax
  volatile signed __int32 *v18; // rsi
  volatile signed __int32 *v19; // r12
  volatile signed __int32 *v20; // rax
  volatile signed __int32 *v21; // r14
  void *v22; // rax
  struct IZnPassThroughProcessor *v23; // r12
  SDK::AgileServer *v24; // rax
  __int64 v25; // r13
  volatile signed __int32 *v26; // rax
  volatile signed __int32 *v27; // rsi
  struct IZnPassThroughProcessor *v28; // rax
  struct IZnPassThroughProcessor *v29; // r12
  volatile signed __int32 *v30; // rcx
  volatile signed __int32 *v31; // rax
  volatile signed __int32 *v32; // r14
  void *v33; // rax
  struct IZnPassThroughProcessor *v34; // rax
  _QWORD v36[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  volatile signed __int32 *v38; // [rsp+50h] [rbp-B0h]
  volatile signed __int32 *v39; // [rsp+58h] [rbp-A8h]
  volatile signed __int32 *v40; // [rsp+60h] [rbp-A0h]
  struct IZnPassThroughProcessor *v41; // [rsp+68h] [rbp-98h]
  __int128 v42; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v43; // [rsp+80h] [rbp-80h]
  __int128 v44; // [rsp+88h] [rbp-78h]
  _QWORD v45[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v46[2]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v47[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v48; // [rsp+C8h] [rbp-38h]
  _QWORD v49[2]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v50[2]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v51[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v52; // [rsp+108h] [rbp+8h]
  __int128 v53; // [rsp+118h] [rbp+18h]
  __int64 v54; // [rsp+128h] [rbp+28h]
  SDK::Unit::BooleanDevice *v55; // [rsp+130h] [rbp+30h]
  __int64 v56; // [rsp+138h] [rbp+38h]
  __int128 v57; // [rsp+140h] [rbp+40h]
  __int128 v58; // [rsp+150h] [rbp+50h]

  v52 = 0;
  v5 = (SDK::LogicalFunction *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  v37 = (__int64)v5;
  if ( v5 )
    v6 = SDK::LogicalFunction::LogicalFunction(v5);
  else
    v6 = 0;
  v37 = v6;
  v54 = v6;
  v7 = (volatile signed __int32 *)operator new(0x18u);
  v8 = v7;
  v36[0] = v7;
  if ( v7 )
  {
    *(_OWORD *)v7 = 0;
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 3) = 1;
    *(_QWORD *)v7 = &std::_Ref_count<SDK::LogicalFunction>::`vftable';
    *((_QWORD *)v7 + 2) = v6;
  }
  else
  {
    v8 = 0;
  }
  *(_QWORD *)&v52 = v6;
  *((_QWORD *)&v52 + 1) = v8;
  v53 = 0;
  v9 = (SDK::Unit::BooleanDevice *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v36[0] = v9;
  if ( v9 )
    v10 = SDK::Unit::BooleanDevice::BooleanDevice(v9);
  else
    v10 = 0;
  v36[0] = v10;
  v55 = v10;
  v11 = (volatile signed __int32 *)operator new(0x18u);
  v12 = v11;
  v39 = v11;
  if ( v11 )
  {
    *(_OWORD *)v11 = 0;
    *((_DWORD *)v11 + 2) = 1;
    *((_DWORD *)v11 + 3) = 1;
    *(_QWORD *)v11 = &std::_Ref_count<SDK::Unit::BooleanDevice>::`vftable';
    *((_QWORD *)v11 + 2) = v10;
  }
  else
  {
    v12 = 0;
  }
  *(_QWORD *)&v53 = v10;
  *((_QWORD *)&v53 + 1) = v12;
  v13 = -2147467261;
  if ( a4 )
  {
    v13 = -2147024882;
    LODWORD(v39) = -2147024882;
    if ( v6 )
    {
      StringRawBuffer_0 = WindowsGetStringRawBuffer_0(string, 0);
      if ( lstrcmpW(L"application/pdf", StringRawBuffer_0) )
      {
        if ( lstrcmpW(L"image/jpeg", StringRawBuffer_0) )
        {
          v34 = (struct IZnPassThroughProcessor *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
          v23 = v34;
          v41 = v34;
          if ( v34 )
          {
            if ( v8 )
            {
              _InterlockedIncrement(v8 + 2);
              _InterlockedIncrement(v8 + 2);
              v37 = v6;
              v38 = v8;
              SDK::UniqueResource::UniqueResource(v34, &v37);
              *(_QWORD *)v23 = &SDK::DerivativeRelation::`vftable';
              if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
                if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
              }
            }
            else
            {
              v37 = v6;
              v38 = 0;
              SDK::UniqueResource::UniqueResource(v34, &v37);
              *(_QWORD *)v23 = &SDK::DerivativeRelation::`vftable';
            }
          }
          else
          {
            v23 = 0;
          }
        }
        else
        {
          v48 = 0;
          v24 = (SDK::AgileServer *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
          if ( v24 )
            v25 = SDK::AgileServer::AgileServer(v24);
          else
            v25 = 0;
          v56 = v25;
          v26 = (volatile signed __int32 *)operator new(0x18u);
          v27 = v26;
          if ( v26 )
          {
            *(_OWORD *)v26 = 0;
            *((_DWORD *)v26 + 2) = 1;
            *((_DWORD *)v26 + 3) = 1;
            *(_QWORD *)v26 = &std::_Ref_count<SDK::AgileServer>::`vftable';
            *((_QWORD *)v26 + 2) = v25;
          }
          else
          {
            v27 = 0;
          }
          *(_QWORD *)&v48 = v25;
          *((_QWORD *)&v48 + 1) = v27;
          v58 = 0;
          v28 = (struct IZnPassThroughProcessor *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
          v29 = v28;
          if ( v28 )
          {
            if ( v27 )
              _InterlockedIncrement(v27 + 2);
            v30 = v12 + 2;
            if ( v12 )
            {
              _InterlockedIncrement(v30);
              *(_QWORD *)v28 = &SDK::EvenSeries::`vftable';
              *((_QWORD *)v28 + 1) = 0;
              *((_QWORD *)v28 + 2) = 0;
              _InterlockedIncrement(v30);
            }
            else
            {
              *(_QWORD *)v28 = &SDK::EvenSeries::`vftable';
              *((_QWORD *)v28 + 1) = 0;
              *((_QWORD *)v28 + 2) = 0;
            }
            *((_QWORD *)v28 + 1) = v36[0];
            *((_QWORD *)v28 + 2) = v12;
            *((_QWORD *)v28 + 3) = 0;
            *((_QWORD *)v28 + 4) = 0;
            if ( v27 )
              _InterlockedIncrement(v27 + 2);
            *((_QWORD *)v28 + 3) = v25;
            *((_QWORD *)v28 + 4) = v27;
            if ( v12 )
            {
              if ( _InterlockedExchangeAdd(v30, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
                if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
              }
            }
            if ( v27 )
            {
              if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
                if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
              }
            }
          }
          else
          {
            v29 = 0;
          }
          v41 = v29;
          v31 = (volatile signed __int32 *)operator new(0x18u);
          v32 = v31;
          if ( v31 )
          {
            *(_OWORD *)v31 = 0;
            *((_DWORD *)v31 + 2) = 1;
            *((_DWORD *)v31 + 3) = 1;
            *(_QWORD *)v31 = &std::_Ref_count<SDK::EvenSeries>::`vftable';
            *((_QWORD *)v31 + 2) = v29;
          }
          else
          {
            v32 = 0;
          }
          v33 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
          if ( v33 )
          {
            if ( v32 )
              _InterlockedIncrement(v32 + 2);
            v49[0] = v29;
            v49[1] = v32;
            if ( v12 )
              _InterlockedIncrement(v12 + 2);
            v50[0] = v36[0];
            v50[1] = v12;
            if ( v8 )
              _InterlockedIncrement(v8 + 2);
            v51[0] = v37;
            v51[1] = v8;
            v23 = (struct IZnPassThroughProcessor *)SDK::EasyArticle::EasyArticle(v33, v51, v50, v49);
          }
          else
          {
            v23 = 0;
          }
          if ( v32 )
          {
            if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
              if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
            }
          }
          if ( v27 )
          {
            if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
              if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
            }
          }
        }
      }
      else
      {
        v44 = 0;
        v15 = (volatile signed __int32 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
        v40 = v15;
        if ( v15 )
        {
          v42 = 0;
          if ( v12 )
            _InterlockedIncrement(v12 + 2);
          *(_QWORD *)&v42 = v10;
          *((_QWORD *)&v42 + 1) = v12;
          v16 = SDK::Unit::TemporaryPolicy::TemporaryPolicy(v15, &v42);
        }
        else
        {
          v16 = 0;
        }
        v43 = v16;
        v17 = (volatile signed __int32 *)operator new(0x18u);
        v18 = v17;
        v40 = v17;
        if ( v17 )
        {
          *(_OWORD *)v17 = 0;
          *((_DWORD *)v17 + 2) = 1;
          *((_DWORD *)v17 + 3) = 1;
          *(_QWORD *)v17 = &std::_Ref_count<SDK::Unit::TemporaryPolicy>::`vftable';
          *((_QWORD *)v17 + 2) = v16;
        }
        else
        {
          v18 = 0;
        }
        *(_QWORD *)&v44 = v16;
        *((_QWORD *)&v44 + 1) = v18;
        v57 = 0;
        v19 = (volatile signed __int32 *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v19 )
          *(_QWORD *)v19 = &SDK::ActiveLicense::`vftable';
        else
          v19 = 0;
        v40 = v19;
        v20 = (volatile signed __int32 *)operator new(0x18u);
        v21 = v20;
        if ( v20 )
        {
          *(_OWORD *)v20 = 0;
          *((_DWORD *)v20 + 2) = 1;
          *((_DWORD *)v20 + 3) = 1;
          *(_QWORD *)v20 = &std::_Ref_count<SDK::ActiveLicense>::`vftable';
          *((_QWORD *)v20 + 2) = v19;
        }
        else
        {
          v21 = 0;
        }
        operator delete(0);
        v22 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v22 )
        {
          if ( v21 )
            _InterlockedIncrement(v21 + 2);
          v45[0] = v19;
          v45[1] = v21;
          if ( v12 )
            _InterlockedIncrement(v12 + 2);
          v46[0] = v36[0];
          v46[1] = v12;
          if ( v18 )
            _InterlockedIncrement(v18 + 2);
          v36[0] = v16;
          v36[1] = v18;
          if ( v8 )
            _InterlockedIncrement(v8 + 2);
          v47[0] = v37;
          v47[1] = v8;
          v23 = (struct IZnPassThroughProcessor *)SDK::GlobalInstruction::GlobalInstruction(
                                                    (_DWORD)v22,
                                                    (unsigned int)v47,
                                                    (unsigned int)v36,
                                                    (unsigned int)v46,
                                                    (__int64)v45);
        }
        else
        {
          v23 = 0;
        }
        if ( v21 )
        {
          if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
            if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
          }
        }
        if ( v18 )
        {
          if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
            if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
          }
        }
      }
      if ( v23 )
      {
        *a4 = v23;
        v13 = 0;
      }
      else
      {
        v13 = (unsigned int)v39;
      }
    }
  }
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18000b210  mov     [rsp-8+arg_0], rbx
0x18000b215  mov     [rsp-8+arg_8], rsi
0x18000b21a  mov     [rsp-8+arg_10], rdi
0x18000b21f  mov     [rsp-8+arg_18], r9
0x18000b224  push    rbp
0x18000b225  push    r12
0x18000b227  push    r13
0x18000b229  push    r14
0x18000b22b  push    r15
0x18000b22d  lea     rbp, [rsp-80h]
0x18000b232  sub     rsp, 180h
0x18000b239  mov     r13, rcx
0x18000b23c  xorps   xmm0, xmm0
0x18000b23f  movups  [rbp+0A0h+var_98], xmm0
0x18000b243  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b24a  mov     ecx, 50h ; 'P'; unsigned __int64
0x18000b24f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b254  mov     [rsp+1A0h+var_158], rax
0x18000b259  test    rax, rax
0x18000b25c  jz      short loc_18000B26B
0x18000b25e  mov     rcx, rax; this
0x18000b261  call    ??0LogicalFunction@SDK@@QEAA@XZ; SDK::LogicalFunction::LogicalFunction(void)
0x18000b266  mov     rsi, rax
0x18000b269  jmp     short loc_18000B26D
0x18000b26b  xor     esi, esi
0x18000b26d  mov     [rsp+1A0h+var_158], rsi
0x18000b272  mov     [rbp+0A0h+var_78], rsi
0x18000b276  mov     ecx, 18h; Size
0x18000b27b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b280  mov     rbx, rax
0x18000b283  mov     [rsp+1A0h+var_168], rax
0x18000b288  test    rax, rax
0x18000b28b  jz      short loc_18000B2B1
0x18000b28d  xorps   xmm0, xmm0
0x18000b290  movups  xmmword ptr [rax], xmm0
0x18000b293  mov     dword ptr [rax+8], 1
0x18000b29a  mov     dword ptr [rax+0Ch], 1
0x18000b2a1  lea     rax, ??_7?$_Ref_count@VLogicalFunction@SDK@@@std@@6B@; const std::_Ref_count<SDK::LogicalFunction>::`vftable'
0x18000b2a8  mov     [rbx], rax
0x18000b2ab  mov     [rbx+10h], rsi
0x18000b2af  jmp     short loc_18000B2B3
0x18000b2b1  xor     ebx, ebx
0x18000b2b3  mov     qword ptr [rbp+0A0h+var_98], rsi
0x18000b2b7  mov     qword ptr [rbp+0A0h+var_98+8], rbx
0x18000b2bb  xorps   xmm0, xmm0
0x18000b2be  movups  [rbp+0A0h+var_88], xmm0
0x18000b2c2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b2c9  mov     ecx, 10h; unsigned __int64
0x18000b2ce  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b2d3  mov     [rsp+1A0h+var_168], rax
0x18000b2d8  test    rax, rax
0x18000b2db  jz      short loc_18000B2EA
0x18000b2dd  mov     rcx, rax; this
0x18000b2e0  call    ??0BooleanDevice@Unit@SDK@@QEAA@XZ; SDK::Unit::BooleanDevice::BooleanDevice(void)
0x18000b2e5  mov     r14, rax
0x18000b2e8  jmp     short loc_18000B2ED
0x18000b2ea  xor     r14d, r14d
0x18000b2ed  mov     [rsp+1A0h+var_168], r14
0x18000b2f2  mov     [rbp+0A0h+var_70], r14
0x18000b2f6  mov     ecx, 18h; Size
0x18000b2fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b300  mov     rdi, rax
0x18000b303  mov     [rsp+1A0h+var_148], rax
0x18000b308  test    rax, rax
0x18000b30b  jz      short loc_18000B331
0x18000b30d  xorps   xmm0, xmm0
0x18000b310  movups  xmmword ptr [rax], xmm0
0x18000b313  mov     dword ptr [rax+8], 1
0x18000b31a  mov     dword ptr [rax+0Ch], 1
0x18000b321  lea     rax, ??_7?$_Ref_count@VBooleanDevice@Unit@SDK@@@std@@6B@; const std::_Ref_count<SDK::Unit::BooleanDevice>::`vftable'
0x18000b328  mov     [rdi], rax
0x18000b32b  mov     [rdi+10h], r14
0x18000b32f  jmp     short loc_18000B333
0x18000b331  xor     edi, edi
0x18000b333  mov     qword ptr [rbp+0A0h+var_88], r14
0x18000b337  mov     qword ptr [rbp+0A0h+var_88+8], rdi
0x18000b33b  mov     r12d, 80004003h
0x18000b341  mov     r15d, 0FFFFFFFFh
0x18000b347  cmp     [rbp+0A0h+arg_18], 0
0x18000b34f  jz      loc_18000B97A
0x18000b355  mov     r12d, 8007000Eh
0x18000b35b  mov     dword ptr [rsp+1A0h+var_148], r12d
0x18000b360  test    rsi, rsi
0x18000b363  jz      loc_18000B97A
0x18000b369  xor     edx, edx; length
0x18000b36b  mov     rcx, r13; string
0x18000b36e  call    WindowsGetStringRawBuffer_0
0x18000b373  mov     r12, rax
0x18000b376  mov     rdx, rax; lpString2
0x18000b379  lea     rcx, String1; "application/pdf"
0x18000b380  call    cs:__imp_lstrcmpW
0x18000b386  test    eax, eax
0x18000b388  jnz     loc_18000B5CB
0x18000b38e  xorps   xmm1, xmm1
0x18000b391  movdqu  [rbp+0A0h+var_118], xmm1
0x18000b396  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b39d  lea     ecx, [rax+18h]; unsigned __int64
0x18000b3a0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b3a5  mov     [rsp+1A0h+var_140], rax
0x18000b3aa  test    rax, rax
0x18000b3ad  jz      short loc_18000B3DD
0x18000b3af  xorps   xmm0, xmm0
0x18000b3b2  movdqu  [rsp+1A0h+var_130], xmm0
0x18000b3b8  test    rdi, rdi
0x18000b3bb  jz      short loc_18000B3C1
0x18000b3bd  lock inc dword ptr [rdi+8]
0x18000b3c1  mov     qword ptr [rsp+1A0h+var_130], r14
0x18000b3c6  mov     qword ptr [rsp+1A0h+var_130+8], rdi
0x18000b3cb  lea     rdx, [rsp+1A0h+var_130]
0x18000b3d0  mov     rcx, rax
0x18000b3d3  call    ??0TemporaryPolicy@Unit@SDK@@QEAA@V?$shared_ptr@VGeneralTime@SDK@@@std@@@Z; SDK::Unit::TemporaryPolicy::TemporaryPolicy(std::shared_ptr<SDK::GeneralTime>)
0x18000b3d8  mov     r13, rax
0x18000b3db  jmp     short loc_18000B3E0
0x18000b3dd  xor     r13d, r13d
0x18000b3e0  mov     [rbp+0A0h+var_120], r13
0x18000b3e4  mov     ecx, 18h; Size
0x18000b3e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b3ee  mov     rsi, rax
0x18000b3f1  mov     [rsp+1A0h+var_140], rax
0x18000b3f6  test    rax, rax
0x18000b3f9  jz      short loc_18000B41F
0x18000b3fb  xorps   xmm0, xmm0
0x18000b3fe  movups  xmmword ptr [rax], xmm0
0x18000b401  mov     dword ptr [rax+8], 1
0x18000b408  mov     dword ptr [rax+0Ch], 1
0x18000b40f  lea     rax, ??_7?$_Ref_count@VTemporaryPolicy@Unit@SDK@@@std@@6B@; const std::_Ref_count<SDK::Unit::TemporaryPolicy>::`vftable'
0x18000b416  mov     [rsi], rax
0x18000b419  mov     [rsi+10h], r13
0x18000b41d  jmp     short loc_18000B421
0x18000b41f  xor     esi, esi
0x18000b421  mov     qword ptr [rbp+0A0h+var_118], r13
0x18000b425  mov     qword ptr [rbp+0A0h+var_118+8], rsi
0x18000b429  xorps   xmm1, xmm1
0x18000b42c  movdqu  [rbp+0A0h+var_60], xmm1
0x18000b431  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b438  mov     ecx, 8; unsigned __int64
0x18000b43d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b442  mov     r12, rax
0x18000b445  test    rax, rax
0x18000b448  jz      short loc_18000B457
0x18000b44a  lea     rax, ??_7ActiveLicense@SDK@@6B@; const SDK::ActiveLicense::`vftable'
0x18000b451  mov     [r12], rax
0x18000b455  jmp     short loc_18000B45A
0x18000b457  xor     r12d, r12d
0x18000b45a  mov     [rsp+1A0h+var_140], r12
0x18000b45f  mov     ecx, 18h; Size
0x18000b464  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b469  mov     r14, rax
0x18000b46c  mov     [rsp+1A0h+var_170], rax
0x18000b471  test    rax, rax
0x18000b474  jz      short loc_18000B49A
0x18000b476  xorps   xmm0, xmm0
0x18000b479  movups  xmmword ptr [rax], xmm0
0x18000b47c  mov     dword ptr [rax+8], 1
0x18000b483  mov     dword ptr [rax+0Ch], 1
0x18000b48a  lea     rax, ??_7?$_Ref_count@VActiveLicense@SDK@@@std@@6B@; const std::_Ref_count<SDK::ActiveLicense>::`vftable'
0x18000b491  mov     [r14], rax
0x18000b494  mov     [r14+10h], r12
0x18000b498  jmp     short loc_18000B49D
0x18000b49a  xor     r14d, r14d
0x18000b49d  mov     edx, 8
0x18000b4a2  xor     ecx, ecx; Block
0x18000b4a4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b4a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b4b0  mov     ecx, 50h ; 'P'; unsigned __int64
0x18000b4b5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b4ba  mov     [rsp+1A0h+var_170], rax
0x18000b4bf  test    rax, rax
0x18000b4c2  jz      short loc_18000B538
0x18000b4c4  test    r14, r14
0x18000b4c7  jz      short loc_18000B4CE
0x18000b4c9  lock inc dword ptr [r14+8]
0x18000b4ce  mov     [rbp+0A0h+var_108], r12
0x18000b4d2  mov     [rbp+0A0h+var_100], r14
0x18000b4d6  test    rdi, rdi
0x18000b4d9  jz      short loc_18000B4DF
0x18000b4db  lock inc dword ptr [rdi+8]
0x18000b4df  mov     rcx, [rsp+1A0h+var_168]
0x18000b4e4  mov     [rbp+0A0h+var_F8], rcx
0x18000b4e8  mov     [rbp+0A0h+var_F0], rdi
0x18000b4ec  test    rsi, rsi
0x18000b4ef  jz      short loc_18000B4F5
0x18000b4f1  lock inc dword ptr [rsi+8]
0x18000b4f5  mov     [rsp+1A0h+var_168], r13
0x18000b4fa  mov     [rsp+1A0h+var_160], rsi
0x18000b4ff  test    rbx, rbx
0x18000b502  jz      short loc_18000B508
0x18000b504  lock inc dword ptr [rbx+8]
0x18000b508  mov     rcx, [rsp+1A0h+var_158]
0x18000b50d  mov     [rbp+0A0h+var_E8], rcx
0x18000b511  mov     [rbp+0A0h+var_E0], rbx
0x18000b515  lea     rcx, [rbp+0A0h+var_108]
0x18000b519  mov     [rsp+1A0h+var_180], rcx
0x18000b51e  lea     r9, [rbp+0A0h+var_F8]
0x18000b522  lea     r8, [rsp+1A0h+var_168]
0x18000b527  lea     rdx, [rbp+0A0h+var_E8]
0x18000b52b  mov     rcx, rax
0x18000b52e  call    ??0GlobalInstruction@SDK@@QEAA@V?$shared_ptr@VLogicalFunction@SDK@@@std@@V?$shared_ptr@VCurvedMessage@SDK@@@3@V?$shared_ptr@VGeneralTime@SDK@@@3@V?$shared_ptr@VActiveLicense@SDK@@@3@@Z; SDK::GlobalInstruction::GlobalInstruction(std::shared_ptr<SDK::LogicalFunction>,std::shared_ptr<SDK::CurvedMessage>,std::shared_ptr<SDK::GeneralTime>,std::shared_ptr<SDK::ActiveLicense>)
0x18000b533  mov     r12, rax
0x18000b536  jmp     short loc_18000B53B
0x18000b538  xor     r12d, r12d
0x18000b53b  test    r14, r14
0x18000b53e  jz      short loc_18000B57C
0x18000b540  mov     eax, r15d
0x18000b543  lock xadd [r14+8], eax
0x18000b549  cmp     eax, 1
0x18000b54c  jnz     short loc_18000B57C
0x18000b54e  mov     rax, [r14]
0x18000b551  mov     rcx, r14
0x18000b554  mov     rax, [rax]
0x18000b557  call    cs:__guard_dispatch_icall_fptr
0x18000b55d  mov     eax, r15d
0x18000b560  lock xadd [r14+0Ch], eax
0x18000b566  cmp     eax, 1
0x18000b569  jnz     short loc_18000B57C
0x18000b56b  mov     rax, [r14]
0x18000b56e  mov     rcx, r14
0x18000b571  mov     rax, [rax+8]
0x18000b575  call    cs:__guard_dispatch_icall_fptr
0x18000b57b  nop
0x18000b57c  test    rsi, rsi
0x18000b57f  jz      loc_18000B961
0x18000b585  mov     eax, r15d
0x18000b588  lock xadd [rsi+8], eax
0x18000b58d  cmp     eax, 1
0x18000b590  jnz     loc_18000B961
0x18000b596  mov     rax, [rsi]
0x18000b599  mov     rcx, rsi
0x18000b59c  mov     rax, [rax]
0x18000b59f  call    cs:__guard_dispatch_icall_fptr
0x18000b5a5  mov     eax, r15d
0x18000b5a8  lock xadd [rsi+0Ch], eax
0x18000b5ad  cmp     eax, 1
0x18000b5b0  jnz     loc_18000B961
0x18000b5b6  mov     rax, [rsi]
0x18000b5b9  mov     rcx, rsi
0x18000b5bc  mov     rax, [rax+8]
0x18000b5c0  call    cs:__guard_dispatch_icall_fptr
0x18000b5c6  jmp     loc_18000B961
0x18000b5cb  mov     rdx, r12; lpString2
0x18000b5ce  lea     rcx, aImageJpeg; "image/jpeg"
0x18000b5d5  call    cs:__imp_lstrcmpW
0x18000b5db  test    eax, eax
0x18000b5dd  jnz     loc_18000B8B6
0x18000b5e3  xorps   xmm1, xmm1
0x18000b5e6  movdqu  [rbp+0A0h+var_D8], xmm1
0x18000b5eb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b5f2  lea     ecx, [rax+30h]; unsigned __int64
0x18000b5f5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b5fa  mov     [rsp+1A0h+var_170], rax
0x18000b5ff  test    rax, rax
0x18000b602  jz      short loc_18000B611
0x18000b604  mov     rcx, rax; this
0x18000b607  call    ??0AgileServer@SDK@@QEAA@XZ; SDK::AgileServer::AgileServer(void)
0x18000b60c  mov     r13, rax
0x18000b60f  jmp     short loc_18000B614
0x18000b611  xor     r13d, r13d
0x18000b614  mov     [rbp+0A0h+var_68], r13
0x18000b618  mov     ecx, 18h; Size
0x18000b61d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b622  mov     rsi, rax
0x18000b625  mov     [rsp+1A0h+var_170], rax
0x18000b62a  test    rax, rax
0x18000b62d  jz      short loc_18000B653
0x18000b62f  xorps   xmm0, xmm0
0x18000b632  movups  xmmword ptr [rax], xmm0
0x18000b635  mov     dword ptr [rax+8], 1
0x18000b63c  mov     dword ptr [rax+0Ch], 1
0x18000b643  lea     rax, ??_7?$_Ref_count@VAgileServer@SDK@@@std@@6B@; const std::_Ref_count<SDK::AgileServer>::`vftable'
0x18000b64a  mov     [rsi], rax
0x18000b64d  mov     [rsi+10h], r13
0x18000b651  jmp     short loc_18000B655
0x18000b653  xor     esi, esi
0x18000b655  mov     qword ptr [rbp+0A0h+var_D8], r13
0x18000b659  mov     qword ptr [rbp+0A0h+var_D8+8], rsi
0x18000b65d  xorps   xmm1, xmm1
0x18000b660  movdqu  [rbp+0A0h+var_50], xmm1
0x18000b665  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b66c  mov     ecx, 28h ; '('; unsigned __int64
0x18000b671  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b676  mov     r12, rax
0x18000b679  mov     [rsp+1A0h+var_170], rax
0x18000b67e  test    rax, rax
0x18000b681  jz      loc_18000B76B
0x18000b687  test    rsi, rsi
0x18000b68a  jz      short loc_18000B690
0x18000b68c  lock inc dword ptr [rsi+8]
0x18000b690  lea     rcx, [rdi+8]
0x18000b694  lea     rdx, ??_7EvenSeries@SDK@@6B@; const SDK::EvenSeries::`vftable'
0x18000b69b  test    rdi, rdi
0x18000b69e  jz      short loc_18000B6B5
0x18000b6a0  lock inc dword ptr [rcx]
0x18000b6a3  mov     [rax], rdx
0x18000b6a6  xor     edx, edx
0x18000b6a8  mov     [rax+8], rdx
0x18000b6ac  mov     [rax+10h], rdx
0x18000b6b0  lock inc dword ptr [rcx]
0x18000b6b3  jmp     short loc_18000B6C2
0x18000b6b5  mov     [rax], rdx
0x18000b6b8  xor     edx, edx
  ... truncated ...
```
