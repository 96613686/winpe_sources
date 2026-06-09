# CRawImageReader::LogInstance(_MF_TELEMETRY_SESSION_LOG_REASON)

- ea: `0x1800ac600`
- end: `0x1800acc38`
- name: `?LogInstance@CRawImageReader@@UEAAXW4_MF_TELEMETRY_SESSION_LOG_REASON@@@Z`
- size: `1592`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800a5344`

## callees

- `0x180001150`
- `0x180001288`
- `0x180002a00`
- `0x1800ac600`
- `0x1800ad174`
- `0x1800b4010`

## pseudocode

```c
_UNKNOWN **__fastcall CRawImageReader::LogInstance(__int64 a1)
{
  _UNKNOWN **result; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx
  int v5; // esi
  GUID *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rcx
  int v43; // eax
  int v44; // ecx
  int v45; // r8d
  int v46; // r9d
  int v47; // [rsp+188h] [rbp-80h] BYREF
  int v48; // [rsp+18Ch] [rbp-7Ch] BYREF
  int v49; // [rsp+190h] [rbp-78h] BYREF
  int v50; // [rsp+194h] [rbp-74h] BYREF
  int v51; // [rsp+198h] [rbp-70h] BYREF
  int v52; // [rsp+19Ch] [rbp-6Ch] BYREF
  int v53; // [rsp+1A0h] [rbp-68h] BYREF
  int v54; // [rsp+1A4h] [rbp-64h] BYREF
  int v55; // [rsp+1A8h] [rbp-60h] BYREF
  __int64 v56; // [rsp+1B0h] [rbp-58h] BYREF
  __int64 v57; // [rsp+1B8h] [rbp-50h] BYREF
  __int64 v58; // [rsp+1C0h] [rbp-48h] BYREF
  __int64 v59; // [rsp+1C8h] [rbp-40h] BYREF
  __int64 v60; // [rsp+1D0h] [rbp-38h] BYREF
  __int64 v61; // [rsp+1D8h] [rbp-30h] BYREF
  __int64 v62; // [rsp+1E0h] [rbp-28h] BYREF
  __int64 v63; // [rsp+1E8h] [rbp-20h] BYREF
  __int64 v64; // [rsp+1F0h] [rbp-18h] BYREF
  __int64 v65; // [rsp+1F8h] [rbp-10h] BYREF
  __int64 v66; // [rsp+200h] [rbp-8h] BYREF
  __int64 v67; // [rsp+208h] [rbp+0h] BYREF
  __int64 v68; // [rsp+210h] [rbp+8h] BYREF
  __int64 v69; // [rsp+218h] [rbp+10h] BYREF
  __int64 v70; // [rsp+220h] [rbp+18h] BYREF
  __int64 v71; // [rsp+228h] [rbp+20h] BYREF
  __int64 v72; // [rsp+230h] [rbp+28h] BYREF
  __int64 v73; // [rsp+238h] [rbp+30h] BYREF
  __int64 v74; // [rsp+240h] [rbp+38h] BYREF
  __int64 v75; // [rsp+248h] [rbp+40h] BYREF
  __int64 v76; // [rsp+250h] [rbp+48h] BYREF
  __int64 v77; // [rsp+258h] [rbp+50h] BYREF
  __int64 v78; // [rsp+260h] [rbp+58h] BYREF
  __int64 v79; // [rsp+268h] [rbp+60h] BYREF
  __int64 v80; // [rsp+270h] [rbp+68h] BYREF
  __int64 v81; // [rsp+278h] [rbp+70h] BYREF
  __int64 v82; // [rsp+280h] [rbp+78h] BYREF
  __int64 v83; // [rsp+288h] [rbp+80h] BYREF
  __int64 v84; // [rsp+290h] [rbp+88h] BYREF
  __int64 v85; // [rsp+298h] [rbp+90h] BYREF
  __int64 v86; // [rsp+2A0h] [rbp+98h] BYREF
  __int64 v87; // [rsp+2A8h] [rbp+A0h] BYREF
  GUID *v88; // [rsp+2B0h] [rbp+A8h] BYREF
  _QWORD v89[2]; // [rsp+2B8h] [rbp+B0h] BYREF
  GUID v90; // [rsp+2C8h] [rbp+C0h] BYREF
  _UNKNOWN *retaddr; // [rsp+2F0h] [rbp+E8h] BYREF

  result = &retaddr;
  v3 = *(_QWORD *)(a1 + 264);
  if ( !v3
    || (result = (_UNKNOWN **)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 320LL))(
                                v3,
                                MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT),
        !(_DWORD)result) )
  {
    v4 = *(_QWORD *)(a1 + 264);
    v5 = 0;
    v90 = GUID_00000000_0000_0000_0000_000000000000;
    if ( v4 )
    {
      v6 = (GUID *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v4 + 280LL))(v4, v89);
      v7 = *(_QWORD *)(a1 + 264);
      v90 = *v6;
      result = (_UNKNOWN **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 296LL))(v7);
      v5 = (int)result;
    }
    if ( *(_BYTE *)(a1 + 100) && (unsigned int)dword_1800E50B8 > 5 )
    {
      result = (_UNKNOWN **)tlgKeywordOn(&dword_1800E50B8, 0x400000000001LL);
      if ( (_BYTE)result )
      {
        v47 = *(_DWORD *)(a1 + 1032);
        v48 = *(_DWORD *)(a1 + 1028);
        v49 = *(_DWORD *)(a1 + 1024);
        v56 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 952) + 72LL))(a1 + 952);
        v8 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 952) + 32LL))(a1 + 952);
        v9 = *(_QWORD *)(a1 + 952);
        v57 = v8;
        v10 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(v9 + 24))(a1 + 952);
        v11 = *(_QWORD *)(a1 + 952);
        v58 = v10;
        v59 = (*(__int64 (__fastcall **)(__int64))(v11 + 40))(a1 + 952);
        v12 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 952) + 48LL))(a1 + 952);
        v13 = *(_QWORD *)(a1 + 880);
        v60 = v12;
        v61 = (*(__int64 (__fastcall **)(__int64))(v13 + 72))(a1 + 880);
        v14 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 880) + 32LL))(a1 + 880);
        v15 = *(_QWORD *)(a1 + 880);
        v62 = v14;
        v16 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(v15 + 24))(a1 + 880);
        v17 = *(_QWORD *)(a1 + 880);
        v63 = v16;
        v64 = (*(__int64 (__fastcall **)(__int64))(v17 + 40))(a1 + 880);
        v18 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 880) + 48LL))(a1 + 880);
        v19 = *(_QWORD *)(a1 + 808);
        v65 = v18;
        v66 = (*(__int64 (__fastcall **)(__int64))(v19 + 72))(a1 + 808);
        v20 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 808) + 32LL))(a1 + 808);
        v21 = *(_QWORD *)(a1 + 808);
        v67 = v20;
        v22 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(v21 + 24))(a1 + 808);
        v23 = *(_QWORD *)(a1 + 808);
        v68 = v22;
        v69 = (*(__int64 (__fastcall **)(__int64))(v23 + 40))(a1 + 808);
        v24 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 808) + 48LL))(a1 + 808);
        v25 = *(_QWORD *)(a1 + 736);
        v70 = v24;
        v71 = (*(__int64 (__fastcall **)(__int64))(v25 + 72))(a1 + 736);
        v26 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 736) + 32LL))(a1 + 736);
        v27 = *(_QWORD *)(a1 + 736);
        v72 = v26;
        v28 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(v27 + 24))(a1 + 736);
        v29 = *(_QWORD *)(a1 + 736);
        v73 = v28;
        v74 = (*(__int64 (__fastcall **)(__int64))(v29 + 40))(a1 + 736);
        v30 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 736) + 48LL))(a1 + 736);
        v31 = *(_QWORD *)(a1 + 664);
        v75 = v30;
        v76 = (*(__int64 (__fastcall **)(__int64))(v31 + 72))(a1 + 664);
        v32 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 664) + 32LL))(a1 + 664);
        v33 = *(_QWORD *)(a1 + 664);
        v77 = v32;
        v34 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(v33 + 24))(a1 + 664);
        v35 = *(_QWORD *)(a1 + 664);
        v78 = v34;
        v79 = (*(__int64 (__fastcall **)(__int64))(v35 + 40))(a1 + 664);
        v36 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 664) + 48LL))(a1 + 664);
        v37 = *(_QWORD *)(a1 + 592);
        v80 = v36;
        v81 = (*(__int64 (__fastcall **)(__int64))(v37 + 72))(a1 + 592);
        v38 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 592) + 32LL))(a1 + 592);
        v39 = *(_QWORD *)(a1 + 592);
        v82 = v38;
        v40 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(v39 + 24))(a1 + 592);
        v41 = *(_QWORD *)(a1 + 592);
        v83 = v40;
        v84 = (*(__int64 (__fastcall **)(__int64))(v41 + 40))(a1 + 592);
        v42 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 592) + 48LL))(a1 + 592);
        v50 = *(_DWORD *)(a1 + 584);
        v51 = *(_DWORD *)(a1 + 580);
        v52 = *(_DWORD *)(a1 + 576);
        v53 = *(_DWORD *)(a1 + 104);
        v43 = *(_DWORD *)(a1 + 108);
        v85 = v42;
        v54 = v43;
        v86 = CMFBaseStringT<char>::PContents(a1 + 424);
        v87 = CMFBaseStringT<char>::PContents(a1 + 272);
        v88 = &v90;
        v55 = v5;
        v89[0] = 0x1000000;
        return (_UNKNOWN **)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                              v44,
                              (unsigned int)byte_1800D6F81,
                              v45,
                              v46,
                              (__int64)v89,
                              (__int64)&v88,
                              (__int64)&v55,
                              (__int64)&v87,
                              (__int64)&v86,
                              (__int64)&v54,
                              (__int64)&v53,
                              (__int64)&v52,
                              (__int64)&v51,
                              (__int64)&v50,
                              (__int64)&v85,
                              (__int64)&v84,
                              (__int64)&v83,
                              (__int64)&v82,
                              (__int64)&v81,
                              (__int64)&v80,
                              (__int64)&v79,
                              (__int64)&v78,
                              (__int64)&v77,
                              (__int64)&v76,
                              (__int64)&v75,
                              (__int64)&v74,
                              (__int64)&v73,
                              (__int64)&v72,
                              (__int64)&v71,
                              (__int64)&v70,
                              (__int64)&v69,
                              (__int64)&v68,
                              (__int64)&v67,
                              (__int64)&v66,
                              (__int64)&v65,
                              (__int64)&v64,
                              (__int64)&v63,
                              (__int64)&v62,
                              (__int64)&v61,
                              (__int64)&v60,
                              (__int64)&v59,
                              (__int64)&v58,
                              (__int64)&v57,
                              (__int64)&v56,
                              (__int64)&v49,
                              (__int64)&v48,
                              (__int64)&v47);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ac600  mov     rax, rsp
0x1800ac603  mov     [rax+10h], rbx
0x1800ac607  mov     [rax+18h], rsi
0x1800ac60b  mov     [rax+20h], rdi
0x1800ac60f  push    rbp
0x1800ac610  lea     rbp, [rax-0E8h]
0x1800ac617  sub     rsp, 2E0h
0x1800ac61e  mov     rax, cs:__security_cookie
0x1800ac625  xor     rax, rsp
0x1800ac628  mov     [rbp+0E0h+var_10], rax
0x1800ac62f  mov     rdi, rcx
0x1800ac632  mov     rcx, [rcx+108h]
0x1800ac639  test    rcx, rcx
0x1800ac63c  jz      short loc_1800AC65C
0x1800ac63e  mov     rax, [rcx]
0x1800ac641  lea     rdx, MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT
0x1800ac648  mov     rax, [rax+140h]
0x1800ac64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac654  test    eax, eax
0x1800ac656  jnz     loc_1800ACC0F
0x1800ac65c  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800ac663  mov     rcx, [rdi+108h]
0x1800ac66a  xor     esi, esi
0x1800ac66c  movdqu  [rbp+0E0h+var_20], xmm0
0x1800ac674  test    rcx, rcx
0x1800ac677  jz      short loc_1800AC6B2
0x1800ac679  mov     rax, [rcx]
0x1800ac67c  lea     rdx, [rbp+0E0h+var_30]
0x1800ac683  mov     rax, [rax+118h]
0x1800ac68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac68f  mov     rcx, [rdi+108h]
0x1800ac696  movups  xmm0, xmmword ptr [rax]
0x1800ac699  movdqu  [rbp+0E0h+var_20], xmm0
0x1800ac6a1  mov     rax, [rcx]
0x1800ac6a4  mov     rax, [rax+128h]
0x1800ac6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac6b0  mov     esi, eax
0x1800ac6b2  cmp     byte ptr [rdi+64h], 0
0x1800ac6b6  jz      loc_1800ACC0F
0x1800ac6bc  cmp     cs:dword_1800E50B8, 5
0x1800ac6c3  jbe     loc_1800ACC0F
0x1800ac6c9  mov     rdx, 400000000001h
0x1800ac6d3  lea     rcx, dword_1800E50B8
0x1800ac6da  call    _tlgKeywordOn
0x1800ac6df  test    al, al
0x1800ac6e1  jz      loc_1800ACC0F
0x1800ac6e7  mov     eax, [rdi+408h]
0x1800ac6ed  lea     rbx, [rdi+3B8h]
0x1800ac6f4  mov     [rbp+0E0h+var_160], eax
0x1800ac6f7  mov     rcx, rbx
0x1800ac6fa  mov     eax, [rdi+404h]
0x1800ac700  mov     [rbp+0E0h+var_15C], eax
0x1800ac703  mov     eax, [rdi+400h]
0x1800ac709  mov     [rbp+0E0h+var_158], eax
0x1800ac70c  mov     rax, [rbx]
0x1800ac70f  mov     rax, [rax+48h]
0x1800ac713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac718  mov     [rbp+0E0h+var_138], rax
0x1800ac71c  mov     rcx, rbx
0x1800ac71f  mov     rax, [rbx]
0x1800ac722  mov     rax, [rax+20h]
0x1800ac726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac72b  mov     rcx, [rax]
0x1800ac72e  mov     rax, [rbx]
0x1800ac731  mov     [rbp+0E0h+var_130], rcx
0x1800ac735  mov     rcx, rbx
0x1800ac738  mov     rax, [rax+18h]
0x1800ac73c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac741  mov     rcx, rbx
0x1800ac744  mov     rdx, [rax]
0x1800ac747  mov     rax, [rbx]
0x1800ac74a  mov     [rbp+0E0h+var_128], rdx
0x1800ac74e  mov     rax, [rax+28h]
0x1800ac752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac757  mov     [rbp+0E0h+var_120], rax
0x1800ac75b  mov     rcx, rbx
0x1800ac75e  mov     rax, [rbx]
0x1800ac761  mov     rax, [rax+30h]
0x1800ac765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac76a  lea     rbx, [rdi+370h]
0x1800ac771  mov     rcx, [rax]
0x1800ac774  mov     rax, [rbx]
0x1800ac777  mov     [rbp+0E0h+var_118], rcx
0x1800ac77b  mov     rcx, rbx
0x1800ac77e  mov     rax, [rax+48h]
0x1800ac782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac787  mov     [rbp+0E0h+var_110], rax
0x1800ac78b  mov     rcx, rbx
0x1800ac78e  mov     rax, [rbx]
0x1800ac791  mov     rax, [rax+20h]
0x1800ac795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac79a  mov     rcx, [rax]
0x1800ac79d  mov     rax, [rbx]
0x1800ac7a0  mov     [rbp+0E0h+var_108], rcx
0x1800ac7a4  mov     rcx, rbx
0x1800ac7a7  mov     rax, [rax+18h]
0x1800ac7ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac7b0  mov     rcx, rbx
0x1800ac7b3  mov     rdx, [rax]
0x1800ac7b6  mov     rax, [rbx]
0x1800ac7b9  mov     [rbp+0E0h+var_100], rdx
0x1800ac7bd  mov     rax, [rax+28h]
0x1800ac7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac7c6  mov     [rbp+0E0h+var_F8], rax
0x1800ac7ca  mov     rcx, rbx
0x1800ac7cd  mov     rax, [rbx]
0x1800ac7d0  mov     rax, [rax+30h]
0x1800ac7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac7d9  lea     rbx, [rdi+328h]
0x1800ac7e0  mov     rcx, [rax]
0x1800ac7e3  mov     rax, [rbx]
0x1800ac7e6  mov     [rbp+0E0h+var_F0], rcx
0x1800ac7ea  mov     rcx, rbx
0x1800ac7ed  mov     rax, [rax+48h]
0x1800ac7f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac7f6  mov     [rbp+0E0h+var_E8], rax
0x1800ac7fa  mov     rcx, rbx
0x1800ac7fd  mov     rax, [rbx]
0x1800ac800  mov     rax, [rax+20h]
0x1800ac804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac809  mov     rcx, [rax]
0x1800ac80c  mov     rax, [rbx]
0x1800ac80f  mov     [rbp+0E0h+var_E0], rcx
0x1800ac813  mov     rcx, rbx
0x1800ac816  mov     rax, [rax+18h]
0x1800ac81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac81f  mov     rdx, [rax]
0x1800ac822  mov     rax, [rbx]
0x1800ac825  mov     rcx, rbx
0x1800ac828  mov     [rbp+0E0h+var_D8], rdx
0x1800ac82c  mov     rax, [rax+28h]
0x1800ac830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac835  mov     [rbp+0E0h+var_D0], rax
0x1800ac839  mov     rcx, rbx
0x1800ac83c  mov     rax, [rbx]
0x1800ac83f  mov     rax, [rax+30h]
0x1800ac843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac848  lea     rbx, [rdi+2E0h]
0x1800ac84f  mov     rcx, [rax]
0x1800ac852  mov     rax, [rbx]
0x1800ac855  mov     [rbp+0E0h+var_C8], rcx
0x1800ac859  mov     rcx, rbx
0x1800ac85c  mov     rax, [rax+48h]
0x1800ac860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac865  mov     [rbp+0E0h+var_C0], rax
0x1800ac869  mov     rcx, rbx
0x1800ac86c  mov     rax, [rbx]
0x1800ac86f  mov     rax, [rax+20h]
0x1800ac873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac878  mov     rcx, [rax]
0x1800ac87b  mov     rax, [rbx]
0x1800ac87e  mov     [rbp+0E0h+var_B8], rcx
0x1800ac882  mov     rcx, rbx
0x1800ac885  mov     rax, [rax+18h]
0x1800ac889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac88e  mov     rcx, rbx
0x1800ac891  mov     rdx, [rax]
0x1800ac894  mov     rax, [rbx]
0x1800ac897  mov     [rbp+0E0h+var_B0], rdx
0x1800ac89b  mov     rax, [rax+28h]
0x1800ac89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac8a4  mov     [rbp+0E0h+var_A8], rax
0x1800ac8a8  mov     rcx, rbx
0x1800ac8ab  mov     rax, [rbx]
0x1800ac8ae  mov     rax, [rax+30h]
0x1800ac8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac8b7  lea     rbx, [rdi+298h]
0x1800ac8be  mov     rcx, [rax]
0x1800ac8c1  mov     rax, [rbx]
0x1800ac8c4  mov     [rbp+0E0h+var_A0], rcx
0x1800ac8c8  mov     rcx, rbx
0x1800ac8cb  mov     rax, [rax+48h]
0x1800ac8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac8d4  mov     [rbp+0E0h+var_98], rax
0x1800ac8d8  mov     rcx, rbx
0x1800ac8db  mov     rax, [rbx]
0x1800ac8de  mov     rax, [rax+20h]
0x1800ac8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac8e7  mov     rcx, [rax]
0x1800ac8ea  mov     rax, [rbx]
0x1800ac8ed  mov     [rbp+0E0h+var_90], rcx
0x1800ac8f1  mov     rcx, rbx
0x1800ac8f4  mov     rax, [rax+18h]
0x1800ac8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac8fd  mov     rcx, rbx
0x1800ac900  mov     rdx, [rax]
0x1800ac903  mov     rax, [rbx]
0x1800ac906  mov     [rbp+0E0h+var_88], rdx
0x1800ac90a  mov     rax, [rax+28h]
0x1800ac90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac913  mov     [rbp+0E0h+var_80], rax
0x1800ac917  mov     rcx, rbx
0x1800ac91a  mov     rax, [rbx]
0x1800ac91d  mov     rax, [rax+30h]
0x1800ac921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac926  lea     rbx, [rdi+250h]
0x1800ac92d  mov     rcx, [rax]
0x1800ac930  mov     rax, [rbx]
0x1800ac933  mov     [rbp+0E0h+var_78], rcx
0x1800ac937  mov     rcx, rbx
0x1800ac93a  mov     rax, [rax+48h]
0x1800ac93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac943  mov     [rbp+0E0h+var_70], rax
0x1800ac947  mov     rcx, rbx
0x1800ac94a  mov     rax, [rbx]
0x1800ac94d  mov     rax, [rax+20h]
0x1800ac951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac956  mov     rcx, [rax]
0x1800ac959  mov     rax, [rbx]
0x1800ac95c  mov     [rbp+0E0h+var_68], rcx
0x1800ac960  mov     rcx, rbx
0x1800ac963  mov     rax, [rax+18h]
0x1800ac967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac96c  mov     rcx, rbx
0x1800ac96f  mov     rdx, [rax]
0x1800ac972  mov     rax, [rbx]
0x1800ac975  mov     [rbp+0E0h+var_60], rdx
0x1800ac97c  mov     rax, [rax+28h]
0x1800ac980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac985  mov     [rbp+0E0h+var_58], rax
0x1800ac98c  mov     rcx, rbx
0x1800ac98f  mov     rax, [rbx]
0x1800ac992  mov     rax, [rax+30h]
0x1800ac996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac99b  mov     rcx, [rax]
0x1800ac99e  mov     eax, [rdi+248h]
0x1800ac9a4  mov     [rbp+0E0h+var_154], eax
0x1800ac9a7  mov     eax, [rdi+244h]
0x1800ac9ad  mov     [rbp+0E0h+var_150], eax
0x1800ac9b0  mov     eax, [rdi+240h]
0x1800ac9b6  mov     [rbp+0E0h+var_14C], eax
0x1800ac9b9  mov     eax, [rdi+68h]
0x1800ac9bc  mov     [rbp+0E0h+var_148], eax
0x1800ac9bf  mov     eax, [rdi+6Ch]
0x1800ac9c2  mov     [rbp+0E0h+var_50], rcx
0x1800ac9c9  lea     rcx, [rdi+1A8h]
0x1800ac9d0  mov     [rbp+0E0h+var_144], eax
0x1800ac9d3  call    ?PContents@?$CMFBaseStringT@D@@QEBAPEBDXZ; CMFBaseStringT<char>::PContents(void)
0x1800ac9d8  lea     rcx, [rdi+110h]
0x1800ac9df  mov     [rbp+0E0h+var_48], rax
0x1800ac9e6  call    ?PContents@?$CMFBaseStringT@D@@QEBAPEBDXZ; CMFBaseStringT<char>::PContents(void)
0x1800ac9eb  mov     [rbp+0E0h+var_40], rax
0x1800ac9f2  lea     rax, [rbp+0E0h+var_20]
0x1800ac9f9  mov     [rbp+0E0h+var_38], rax
0x1800aca00  lea     rax, [rbp+0E0h+var_160]
0x1800aca04  mov     [rsp+2E0h+var_170], rax
0x1800aca0c  lea     rax, [rbp+0E0h+var_15C]
0x1800aca10  mov     [rsp+2E0h+var_178], rax
0x1800aca18  lea     rax, [rbp+0E0h+var_158]
0x1800aca1c  mov     [rsp+2E0h+var_180], rax
0x1800aca24  lea     rax, [rbp+0E0h+var_138]
0x1800aca28  mov     [rsp+2E0h+var_188], rax
0x1800aca30  lea     rax, [rbp+0E0h+var_130]
0x1800aca34  mov     [rsp+2E0h+var_190], rax
0x1800aca3c  lea     rax, [rbp+0E0h+var_128]
0x1800aca40  mov     [rsp+2E0h+var_198], rax
0x1800aca48  lea     rax, [rbp+0E0h+var_120]
0x1800aca4c  mov     [rsp+2E0h+var_1A0], rax
0x1800aca54  lea     rax, [rbp+0E0h+var_118]
0x1800aca58  mov     [rsp+2E0h+var_1A8], rax
0x1800aca60  lea     rax, [rbp+0E0h+var_110]
0x1800aca64  mov     [rsp+2E0h+var_1B0], rax
0x1800aca6c  lea     rax, [rbp+0E0h+var_108]
0x1800aca70  mov     [rsp+2E0h+var_1B8], rax
0x1800aca78  lea     rax, [rbp+0E0h+var_100]
0x1800aca7c  mov     [rsp+2E0h+var_1C0], rax
0x1800aca84  lea     rax, [rbp+0E0h+var_F8]
0x1800aca88  mov     [rsp+2E0h+var_1C8], rax
0x1800aca90  lea     rax, [rbp+0E0h+var_F0]
0x1800aca94  mov     [rsp+2E0h+var_1D0], rax
0x1800aca9c  lea     rax, [rbp+0E0h+var_E8]
0x1800acaa0  mov     [rsp+2E0h+var_1D8], rax
0x1800acaa8  lea     rax, [rbp+0E0h+var_E0]
0x1800acaac  mov     [rsp+2E0h+var_1E0], rax
0x1800acab4  lea     rax, [rbp+0E0h+var_D8]
0x1800acab8  mov     [rsp+2E0h+var_1E8], rax
0x1800acac0  lea     rax, [rbp+0E0h+var_D0]
0x1800acac4  mov     [rsp+2E0h+var_1F0], rax
0x1800acacc  lea     rax, [rbp+0E0h+var_C8]
0x1800acad0  mov     [rsp+2E0h+var_1F8], rax
0x1800acad8  lea     rax, [rbp+0E0h+var_C0]
0x1800acadc  mov     [rsp+2E0h+var_200], rax
0x1800acae4  lea     rax, [rbp+0E0h+var_B8]
0x1800acae8  mov     [rsp+2E0h+var_208], rax
0x1800acaf0  lea     rax, [rbp+0E0h+var_B0]
0x1800acaf4  mov     [rsp+2E0h+var_210], rax
0x1800acafc  lea     rax, [rbp+0E0h+var_A8]
0x1800acb00  mov     [rbp+0E0h+var_140], esi
0x1800acb03  mov     [rbp+0E0h+var_30], 1000000h
0x1800acb0e  mov     [rsp+2E0h+var_218], rax
0x1800acb16  lea     rdx, byte_1800D6F81
0x1800acb1d  lea     rax, [rbp+0E0h+var_A0]
0x1800acb21  mov     [rsp+2E0h+var_220], rax
0x1800acb29  lea     rax, [rbp+0E0h+var_98]
0x1800acb2d  mov     [rsp+2E0h+var_228], rax
0x1800acb35  lea     rax, [rbp+0E0h+var_90]
0x1800acb39  mov     [rsp+2E0h+var_230], rax
0x1800acb41  lea     rax, [rbp+0E0h+var_88]
0x1800acb45  mov     [rsp+2E0h+var_238], rax
0x1800acb4d  lea     rax, [rbp+0E0h+var_80]
  ... truncated ...
```
