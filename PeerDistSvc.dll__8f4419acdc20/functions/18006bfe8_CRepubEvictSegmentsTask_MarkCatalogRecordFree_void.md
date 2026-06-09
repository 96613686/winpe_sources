# CRepubEvictSegmentsTask::MarkCatalogRecordFree(void)

- ea: `0x18006bfe8`
- end: `0x18006c6d0`
- name: `?MarkCatalogRecordFree@CRepubEvictSegmentsTask@@IEAAKXZ`
- size: `1768`
- prototype: `unsigned int __fastcall(CRepubEvictSegmentsTask *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x180067cf8`

## callees

- `0x180008290`
- `0x18000ceac`
- `0x18006bfe8`
- `0x1801448c0`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x18006c53c`
- `ESENT!JetPrepareUpdate` at `0x18006c53c`
- `ESENT!JetSetColumns` at `0x18006c5c2`
- `ESENT!JetSetColumns` at `0x18006c5c2`
- `ESENT!JetUpdate` at `0x18006c627`
- `ESENT!JetUpdate` at `0x18006c627`

## pseudocode

```c
__int64 __fastcall CRepubEvictSegmentsTask::MarkCatalogRecordFree(CRepubEvictSegmentsTask *this)
{
  __int64 v2; // rax
  int v3; // ecx
  __int64 v4; // rax
  int v5; // ecx
  __int64 v6; // rax
  int v7; // ecx
  __int64 v8; // rax
  int v9; // ecx
  __int64 v10; // rax
  int v11; // ecx
  __int64 v12; // rax
  int v13; // ecx
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // rax
  int v17; // ecx
  __int64 v18; // rax
  int v19; // ecx
  __int64 v20; // rax
  int v21; // ecx
  __int64 v22; // rax
  int v23; // ecx
  __int64 v24; // rax
  int v25; // ecx
  __int64 v26; // rax
  int v27; // ecx
  __int64 v28; // rax
  int v29; // ecx
  __int64 v30; // rax
  int v31; // ecx
  __int64 v32; // rax
  int v33; // ecx
  __int64 v34; // rax
  int v35; // ecx
  __int64 v36; // rax
  int v37; // ecx
  __int64 v38; // rax
  unsigned int v39; // esi
  unsigned int v40; // edi
  CHostedCacheMsgEncoding *v41; // rcx
  __int64 v42; // rdx
  unsigned int v43; // eax
  unsigned int v44; // eax
  __int16 v46; // [rsp+30h] [rbp-29h] BYREF
  int v47; // [rsp+34h] [rbp-25h] BYREF
  int v48; // [rsp+38h] [rbp-21h] BYREF
  int v49; // [rsp+3Ch] [rbp-1Dh] BYREF
  int v50; // [rsp+40h] [rbp-19h] BYREF
  int v51; // [rsp+44h] [rbp-15h] BYREF
  int v52; // [rsp+48h] [rbp-11h] BYREF
  int v53; // [rsp+4Ch] [rbp-Dh] BYREF
  int v54; // [rsp+50h] [rbp-9h] BYREF
  int v55; // [rsp+54h] [rbp-5h] BYREF
  __int64 v56; // [rsp+58h] [rbp-1h] BYREF
  __int64 v57; // [rsp+60h] [rbp+7h] BYREF
  __int64 v58; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v59; // [rsp+70h] [rbp+17h] BYREF

  v57 = -1;
  v55 = 0;
  v48 = 0;
  v56 = 0x7FFFFFFFFFFFFFFFLL;
  v2 = *((_QWORD *)this + 51);
  v47 = 1;
  v49 = 0;
  v50 = 0;
  v58 = 0;
  v46 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v59 = 0;
  v3 = *(_DWORD *)(v2 + 856);
  v4 = *((_QWORD *)this + 50);
  *(_DWORD *)(v4 + 4) = 0;
  *(_QWORD *)(v4 + 20) = 0;
  *(_QWORD *)(v4 + 32) = 0;
  *(_DWORD *)v4 = v3;
  *(_QWORD *)(v4 + 8) = &v56;
  *(_DWORD *)(v4 + 16) = 8;
  *(_DWORD *)(v4 + 28) = 1;
  v5 = *(_DWORD *)(*((_QWORD *)this + 51) + 824LL);
  v6 = *((_QWORD *)this + 50);
  *(_DWORD *)(v6 + 44) = 0;
  *(_QWORD *)(v6 + 60) = 0;
  *(_QWORD *)(v6 + 72) = 0;
  *(_DWORD *)(v6 + 40) = v5;
  *(_QWORD *)(v6 + 48) = &v47;
  *(_DWORD *)(v6 + 56) = 1;
  *(_DWORD *)(v6 + 68) = 1;
  v7 = *(_DWORD *)(*((_QWORD *)this + 51) + 828LL);
  v8 = *((_QWORD *)this + 50);
  *(_DWORD *)(v8 + 84) = 0;
  *(_QWORD *)(v8 + 100) = 0;
  *(_QWORD *)(v8 + 112) = 0;
  *(_DWORD *)(v8 + 80) = v7;
  *(_QWORD *)(v8 + 88) = &v48;
  *(_DWORD *)(v8 + 96) = 1;
  *(_DWORD *)(v8 + 108) = 1;
  v9 = *(_DWORD *)(*((_QWORD *)this + 51) + 832LL);
  v10 = *((_QWORD *)this + 50);
  *(_DWORD *)(v10 + 124) = 0;
  *(_QWORD *)(v10 + 140) = 0;
  *(_QWORD *)(v10 + 152) = 0;
  *(_DWORD *)(v10 + 120) = v9;
  *(_QWORD *)(v10 + 128) = &v49;
  *(_DWORD *)(v10 + 136) = 4;
  *(_DWORD *)(v10 + 148) = 1;
  v11 = *(_DWORD *)(*((_QWORD *)this + 51) + 836LL);
  v12 = *((_QWORD *)this + 50);
  *(_DWORD *)(v12 + 164) = 0;
  *(_QWORD *)(v12 + 180) = 0;
  *(_QWORD *)(v12 + 192) = 0;
  *(_DWORD *)(v12 + 160) = v11;
  *(_QWORD *)(v12 + 168) = &v50;
  *(_DWORD *)(v12 + 176) = 4;
  *(_DWORD *)(v12 + 188) = 1;
  v13 = *(_DWORD *)(*((_QWORD *)this + 51) + 840LL);
  v14 = *((_QWORD *)this + 50);
  *(_DWORD *)(v14 + 204) = 0;
  *(_QWORD *)(v14 + 220) = 0;
  *(_QWORD *)(v14 + 232) = 0;
  *(_DWORD *)(v14 + 200) = v13;
  *(_QWORD *)(v14 + 208) = &v57;
  *(_DWORD *)(v14 + 216) = 8;
  *(_DWORD *)(v14 + 228) = 1;
  v15 = *(_DWORD *)(*((_QWORD *)this + 51) + 844LL);
  v16 = *((_QWORD *)this + 50);
  *(_DWORD *)(v16 + 244) = 0;
  *(_QWORD *)(v16 + 260) = 0;
  *(_QWORD *)(v16 + 272) = 0;
  *(_DWORD *)(v16 + 240) = v15;
  *(_QWORD *)(v16 + 248) = &v58;
  *(_DWORD *)(v16 + 256) = 8;
  *(_DWORD *)(v16 + 268) = 1;
  v17 = *(_DWORD *)(*((_QWORD *)this + 51) + 848LL);
  v18 = *((_QWORD *)this + 50);
  *(_DWORD *)(v18 + 284) = 0;
  *(_QWORD *)(v18 + 300) = 0;
  *(_QWORD *)(v18 + 312) = 0;
  *(_DWORD *)(v18 + 280) = v17;
  *(_QWORD *)(v18 + 288) = &v46;
  *(_DWORD *)(v18 + 296) = 2;
  *(_DWORD *)(v18 + 308) = 1;
  v19 = *(_DWORD *)(*((_QWORD *)this + 51) + 852LL);
  v20 = *((_QWORD *)this + 50);
  *(_DWORD *)(v20 + 324) = 0;
  *(_QWORD *)(v20 + 340) = 0;
  *(_QWORD *)(v20 + 352) = 0;
  *(_DWORD *)(v20 + 320) = v19;
  *(_QWORD *)(v20 + 328) = &v51;
  *(_DWORD *)(v20 + 336) = 4;
  *(_DWORD *)(v20 + 348) = 1;
  v21 = *(_DWORD *)(*((_QWORD *)this + 51) + 860LL);
  v22 = *((_QWORD *)this + 50);
  *(_DWORD *)(v22 + 364) = 0;
  *(_QWORD *)(v22 + 380) = 0;
  *(_QWORD *)(v22 + 392) = 0;
  *(_DWORD *)(v22 + 360) = v21;
  *(_QWORD *)(v22 + 368) = &v52;
  *(_DWORD *)(v22 + 376) = 4;
  *(_DWORD *)(v22 + 388) = 1;
  v23 = *(_DWORD *)(*((_QWORD *)this + 51) + 864LL);
  v24 = *((_QWORD *)this + 50);
  *(_DWORD *)(v24 + 404) = 0;
  *(_QWORD *)(v24 + 420) = 0;
  *(_QWORD *)(v24 + 432) = 0;
  *(_DWORD *)(v24 + 400) = v23;
  *(_QWORD *)(v24 + 408) = &v53;
  *(_DWORD *)(v24 + 416) = 4;
  *(_DWORD *)(v24 + 428) = 1;
  v25 = *(_DWORD *)(*((_QWORD *)this + 51) + 868LL);
  v26 = *((_QWORD *)this + 50);
  *(_DWORD *)(v26 + 444) = 0;
  *(_QWORD *)(v26 + 460) = 0;
  *(_QWORD *)(v26 + 472) = 0;
  *(_DWORD *)(v26 + 440) = v25;
  *(_QWORD *)(v26 + 448) = &v54;
  *(_DWORD *)(v26 + 456) = 4;
  *(_DWORD *)(v26 + 468) = 1;
  v27 = *(_DWORD *)(*((_QWORD *)this + 51) + 872LL);
  v28 = *((_QWORD *)this + 50);
  *(_DWORD *)(v28 + 484) = 0;
  *(_QWORD *)(v28 + 500) = 0;
  *(_QWORD *)(v28 + 512) = 0;
  *(_DWORD *)(v28 + 480) = v27;
  *(_DWORD *)(v28 + 496) = 4;
  *(_DWORD *)(v28 + 508) = 1;
  *(_QWORD *)(v28 + 488) = &v55;
  v29 = *(_DWORD *)(*((_QWORD *)this + 51) + 876LL);
  v30 = *((_QWORD *)this + 50);
  *(_DWORD *)(v30 + 524) = 0;
  *(_QWORD *)(v30 + 540) = 0;
  *(_QWORD *)(v30 + 552) = 0;
  *(_DWORD *)(v30 + 520) = v29;
  *(_QWORD *)(v30 + 528) = &v59;
  *(_DWORD *)(v30 + 536) = 16;
  *(_DWORD *)(v30 + 548) = 1;
  v31 = *(_DWORD *)(*((_QWORD *)this + 51) + 880LL);
  v32 = *((_QWORD *)this + 50);
  *(_DWORD *)(v32 + 564) = 0;
  *(_QWORD *)(v32 + 580) = 0;
  *(_QWORD *)(v32 + 592) = 0;
  *(_DWORD *)(v32 + 560) = v31;
  *(_DWORD *)(v32 + 576) = 0;
  *(_QWORD *)(v32 + 568) = 0;
  *(_DWORD *)(v32 + 588) = 1;
  v33 = *(_DWORD *)(*((_QWORD *)this + 51) + 884LL);
  v34 = *((_QWORD *)this + 50);
  *(_DWORD *)(v34 + 604) = 0;
  *(_QWORD *)(v34 + 620) = 0;
  *(_QWORD *)(v34 + 632) = 0;
  *(_DWORD *)(v34 + 600) = v33;
  *(_DWORD *)(v34 + 616) = 0;
  *(_QWORD *)(v34 + 608) = 0;
  *(_DWORD *)(v34 + 628) = 1;
  v35 = *(_DWORD *)(*((_QWORD *)this + 51) + 888LL);
  v36 = *((_QWORD *)this + 50);
  *(_DWORD *)(v36 + 644) = 0;
  *(_QWORD *)(v36 + 660) = 0;
  *(_QWORD *)(v36 + 672) = 0;
  *(_DWORD *)(v36 + 640) = v35;
  *(_DWORD *)(v36 + 656) = 0;
  *(_QWORD *)(v36 + 648) = 0;
  *(_DWORD *)(v36 + 668) = 1;
  v37 = *(_DWORD *)(*((_QWORD *)this + 51) + 892LL);
  v38 = *((_QWORD *)this + 50);
  *(_DWORD *)(v38 + 684) = 0;
  *(_QWORD *)(v38 + 700) = 0;
  *(_QWORD *)(v38 + 712) = 0;
  *(_DWORD *)(v38 + 680) = v37;
  *(_DWORD *)(v38 + 696) = 0;
  *(_QWORD *)(v38 + 688) = 0;
  *(_DWORD *)(v38 + 708) = 1;
  v39 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 62), 2u);
  if ( !v39 )
  {
    v43 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 62), *((JET_SETCOLUMN **)this + 50), 0x12u);
    if ( v43 )
    {
      v40 = (*(__int64 (__fastcall **)(CRepubEvictSegmentsTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v43);
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        return v40;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        goto LABEL_18;
      v42 = 280;
    }
    else
    {
      v40 = 0;
      v44 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 62), 0, 0, 0);
      if ( !v44 )
        goto LABEL_17;
      v40 = (*(__int64 (__fastcall **)(CRepubEvictSegmentsTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v44);
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        return v40;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        goto LABEL_18;
      v42 = 281;
    }
LABEL_6:
    WPP_SF_Dd(*((_QWORD *)v41 + 12), v42, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
LABEL_17:
    v41 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v40 = (*(__int64 (__fastcall **)(CRepubEvictSegmentsTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v39);
  v41 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    return v40;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v42 = 279;
    goto LABEL_6;
  }
LABEL_18:
  if ( v41 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v41 + 108) & 4) != 0
    && *((_BYTE *)v41 + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)v41 + 12), 282, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v40);
  }
  return v40;
}

```

## disassembly

```asm
0x18006bfe8  mov     [rsp-8+arg_8], rbx
0x18006bfed  mov     [rsp-8+arg_10], rsi
0x18006bff2  push    rbp
0x18006bff3  push    rdi
0x18006bff4  push    r13
0x18006bff6  push    r14
0x18006bff8  push    r15
0x18006bffa  lea     rbp, [rsp-37h]
0x18006bfff  sub     rsp, 90h
0x18006c006  mov     rax, cs:__security_cookie
0x18006c00d  xor     rax, rsp
0x18006c010  mov     [rbp+57h+var_30], rax
0x18006c014  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFFh
0x18006c01c  xor     r14d, r14d
0x18006c01f  mov     [rbp+57h+var_5C], r14d
0x18006c023  mov     rbx, rcx
0x18006c026  mov     [rbp+57h+var_78], r14d
0x18006c02a  mov     rax, 7FFFFFFFFFFFFFFFh
0x18006c034  mov     [rbp+57h+var_58], rax
0x18006c038  xorps   xmm0, xmm0
0x18006c03b  mov     rax, [rcx+198h]
0x18006c042  lea     r13d, [r14+1]
0x18006c046  mov     [rbp+57h+var_7C], r13d
0x18006c04a  lea     edx, [r14+8]
0x18006c04e  mov     [rbp+57h+var_74], r14d
0x18006c052  lea     r15d, [r14+4]
0x18006c056  mov     [rbp+57h+var_70], r14d
0x18006c05a  mov     [rbp+57h+var_48], r14
0x18006c05e  mov     [rbp+57h+var_80], r14w
0x18006c063  mov     [rbp+57h+var_6C], r14d
0x18006c067  mov     [rbp+57h+var_68], r14d
0x18006c06b  mov     [rbp+57h+var_64], r14d
0x18006c06f  mov     [rbp+57h+var_60], r14d
0x18006c073  movups  [rbp+57h+var_40], xmm0
0x18006c077  mov     ecx, [rax+358h]
0x18006c07d  mov     rax, [rbx+190h]
0x18006c084  mov     [rax+4], r14d
0x18006c088  mov     [rax+14h], r14
0x18006c08c  mov     [rax+20h], r14
0x18006c090  mov     [rax], ecx
0x18006c092  lea     rcx, [rbp+57h+var_58]
0x18006c096  mov     [rax+8], rcx
0x18006c09a  mov     [rax+10h], edx
0x18006c09d  mov     [rax+1Ch], r13d
0x18006c0a1  mov     rax, [rbx+198h]
0x18006c0a8  mov     ecx, [rax+338h]
0x18006c0ae  mov     rax, [rbx+190h]
0x18006c0b5  mov     [rax+2Ch], r14d
0x18006c0b9  mov     [rax+3Ch], r14
0x18006c0bd  mov     [rax+48h], r14
0x18006c0c1  mov     [rax+28h], ecx
0x18006c0c4  lea     rcx, [rbp+57h+var_7C]
0x18006c0c8  mov     [rax+30h], rcx
0x18006c0cc  mov     [rax+38h], r13d
0x18006c0d0  mov     [rax+44h], r13d
0x18006c0d4  mov     rax, [rbx+198h]
0x18006c0db  mov     ecx, [rax+33Ch]
0x18006c0e1  mov     rax, [rbx+190h]
0x18006c0e8  mov     [rax+54h], r14d
0x18006c0ec  mov     [rax+64h], r14
0x18006c0f0  mov     [rax+70h], r14
0x18006c0f4  mov     [rax+50h], ecx
0x18006c0f7  lea     rcx, [rbp+57h+var_78]
0x18006c0fb  mov     [rax+58h], rcx
0x18006c0ff  mov     [rax+60h], r13d
0x18006c103  mov     [rax+6Ch], r13d
0x18006c107  mov     rax, [rbx+198h]
0x18006c10e  mov     ecx, [rax+340h]
0x18006c114  mov     rax, [rbx+190h]
0x18006c11b  mov     [rax+7Ch], r14d
0x18006c11f  mov     [rax+8Ch], r14
0x18006c126  mov     [rax+98h], r14
0x18006c12d  mov     [rax+78h], ecx
0x18006c130  lea     rcx, [rbp+57h+var_74]
0x18006c134  mov     [rax+80h], rcx
0x18006c13b  mov     [rax+88h], r15d
0x18006c142  mov     [rax+94h], r13d
0x18006c149  mov     rax, [rbx+198h]
0x18006c150  mov     ecx, [rax+344h]
0x18006c156  mov     rax, [rbx+190h]
0x18006c15d  mov     [rax+0A4h], r14d
0x18006c164  mov     [rax+0B4h], r14
0x18006c16b  mov     [rax+0C0h], r14
0x18006c172  mov     [rax+0A0h], ecx
0x18006c178  lea     rcx, [rbp+57h+var_70]
0x18006c17c  mov     [rax+0A8h], rcx
0x18006c183  mov     [rax+0B0h], r15d
0x18006c18a  mov     [rax+0BCh], r13d
0x18006c191  mov     rax, [rbx+198h]
0x18006c198  mov     ecx, [rax+348h]
0x18006c19e  mov     rax, [rbx+190h]
0x18006c1a5  mov     [rax+0CCh], r14d
0x18006c1ac  mov     [rax+0DCh], r14
0x18006c1b3  mov     [rax+0E8h], r14
0x18006c1ba  lea     r8d, [r14+2]; prep
0x18006c1be  mov     [rax+0C8h], ecx
0x18006c1c4  lea     rcx, [rbp+57h+var_50]
0x18006c1c8  mov     [rax+0D0h], rcx
0x18006c1cf  mov     [rax+0D8h], edx
0x18006c1d5  mov     [rax+0E4h], r13d
0x18006c1dc  mov     rax, [rbx+198h]
0x18006c1e3  mov     ecx, [rax+34Ch]
0x18006c1e9  mov     rax, [rbx+190h]
0x18006c1f0  mov     [rax+0F4h], r14d
0x18006c1f7  mov     [rax+104h], r14
0x18006c1fe  mov     [rax+110h], r14
0x18006c205  mov     [rax+0F0h], ecx
0x18006c20b  lea     rcx, [rbp+57h+var_48]
0x18006c20f  mov     [rax+0F8h], rcx
0x18006c216  mov     [rax+100h], edx
0x18006c21c  mov     [rax+10Ch], r13d
0x18006c223  mov     rax, [rbx+198h]
0x18006c22a  mov     ecx, [rax+350h]
0x18006c230  mov     rax, [rbx+190h]
0x18006c237  mov     [rax+11Ch], r14d
0x18006c23e  mov     [rax+12Ch], r14
0x18006c245  mov     [rax+138h], r14
0x18006c24c  mov     [rax+118h], ecx
0x18006c252  lea     rcx, [rbp+57h+var_80]
0x18006c256  mov     [rax+120h], rcx
0x18006c25d  mov     [rax+128h], r8d
0x18006c264  mov     [rax+134h], r13d
0x18006c26b  mov     rax, [rbx+198h]
0x18006c272  mov     ecx, [rax+354h]
0x18006c278  mov     rax, [rbx+190h]
0x18006c27f  mov     [rax+144h], r14d
0x18006c286  mov     [rax+154h], r14
0x18006c28d  mov     [rax+160h], r14
0x18006c294  mov     [rax+140h], ecx
0x18006c29a  lea     rcx, [rbp+57h+var_6C]
0x18006c29e  mov     [rax+148h], rcx
0x18006c2a5  mov     [rax+150h], r15d
0x18006c2ac  mov     [rax+15Ch], r13d
0x18006c2b3  mov     rax, [rbx+198h]
0x18006c2ba  mov     ecx, [rax+35Ch]
0x18006c2c0  mov     rax, [rbx+190h]
0x18006c2c7  mov     [rax+16Ch], r14d
0x18006c2ce  mov     [rax+17Ch], r14
0x18006c2d5  mov     [rax+188h], r14
0x18006c2dc  mov     [rax+168h], ecx
0x18006c2e2  lea     rcx, [rbp+57h+var_68]
0x18006c2e6  mov     [rax+170h], rcx
0x18006c2ed  mov     [rax+178h], r15d
0x18006c2f4  mov     [rax+184h], r13d
0x18006c2fb  mov     rax, [rbx+198h]
0x18006c302  mov     ecx, [rax+360h]
0x18006c308  mov     rax, [rbx+190h]
0x18006c30f  mov     [rax+194h], r14d
0x18006c316  mov     [rax+1A4h], r14
0x18006c31d  mov     [rax+1B0h], r14
0x18006c324  mov     [rax+190h], ecx
0x18006c32a  lea     rcx, [rbp+57h+var_64]
0x18006c32e  mov     [rax+198h], rcx
0x18006c335  mov     [rax+1A0h], r15d
0x18006c33c  mov     [rax+1ACh], r13d
0x18006c343  mov     rax, [rbx+198h]
0x18006c34a  mov     ecx, [rax+364h]
0x18006c350  mov     rax, [rbx+190h]
0x18006c357  mov     [rax+1BCh], r14d
0x18006c35e  mov     [rax+1CCh], r14
0x18006c365  mov     [rax+1D8h], r14
0x18006c36c  mov     [rax+1B8h], ecx
0x18006c372  lea     rcx, [rbp+57h+var_60]
0x18006c376  mov     [rax+1C0h], rcx
0x18006c37d  mov     [rax+1C8h], r15d
0x18006c384  mov     [rax+1D4h], r13d
0x18006c38b  mov     rax, [rbx+198h]
0x18006c392  mov     ecx, [rax+368h]
0x18006c398  mov     rax, [rbx+190h]
0x18006c39f  mov     [rax+1E4h], r14d
0x18006c3a6  mov     [rax+1F4h], r14
0x18006c3ad  mov     [rax+200h], r14
0x18006c3b4  mov     [rax+1E0h], ecx
0x18006c3ba  mov     [rax+1F0h], r15d
0x18006c3c1  mov     [rax+1FCh], r13d
0x18006c3c8  lea     rcx, [rbp+57h+var_5C]
0x18006c3cc  mov     [rax+1E8h], rcx
0x18006c3d3  mov     rax, [rbx+198h]
0x18006c3da  mov     ecx, [rax+36Ch]
0x18006c3e0  mov     rax, [rbx+190h]
0x18006c3e7  mov     [rax+20Ch], r14d
0x18006c3ee  mov     [rax+21Ch], r14
0x18006c3f5  mov     [rax+228h], r14
0x18006c3fc  mov     [rax+208h], ecx
0x18006c402  lea     rcx, [rbp+57h+var_40]
0x18006c406  mov     [rax+210h], rcx
0x18006c40d  mov     dword ptr [rax+218h], 10h
0x18006c417  mov     [rax+224h], r13d
0x18006c41e  mov     rax, [rbx+198h]
0x18006c425  mov     ecx, [rax+370h]
0x18006c42b  mov     rax, [rbx+190h]
0x18006c432  mov     [rax+234h], r14d
0x18006c439  mov     [rax+244h], r14
0x18006c440  mov     [rax+250h], r14
0x18006c447  mov     [rax+230h], ecx
0x18006c44d  mov     [rax+240h], r14d
0x18006c454  mov     [rax+238h], r14
0x18006c45b  mov     [rax+24Ch], r13d
0x18006c462  mov     rax, [rbx+198h]
0x18006c469  mov     ecx, [rax+374h]
0x18006c46f  mov     rax, [rbx+190h]
0x18006c476  mov     [rax+25Ch], r14d
0x18006c47d  mov     [rax+26Ch], r14
0x18006c484  mov     [rax+278h], r14
0x18006c48b  mov     [rax+258h], ecx
0x18006c491  mov     [rax+268h], r14d
0x18006c498  mov     [rax+260h], r14
0x18006c49f  mov     [rax+274h], r13d
0x18006c4a6  mov     rax, [rbx+198h]
0x18006c4ad  mov     ecx, [rax+378h]
0x18006c4b3  mov     rax, [rbx+190h]
0x18006c4ba  mov     [rax+284h], r14d
0x18006c4c1  mov     [rax+294h], r14
0x18006c4c8  mov     [rax+2A0h], r14
0x18006c4cf  mov     [rax+280h], ecx
0x18006c4d5  mov     [rax+290h], r14d
0x18006c4dc  mov     [rax+288h], r14
0x18006c4e3  mov     [rax+29Ch], r13d
0x18006c4ea  mov     rax, [rbx+198h]
0x18006c4f1  mov     ecx, [rax+37Ch]
0x18006c4f7  mov     rax, [rbx+190h]
0x18006c4fe  mov     [rax+2ACh], r14d
0x18006c505  mov     [rax+2BCh], r14
0x18006c50c  mov     [rax+2C8h], r14
0x18006c513  mov     [rax+2A8h], ecx
0x18006c519  mov     [rax+2B8h], r14d
0x18006c520  mov     [rax+2B0h], r14
0x18006c527  mov     [rax+2C4h], r13d
0x18006c52e  mov     rdx, [rbx+1F0h]; tableid
0x18006c535  mov     rcx, [rbx+178h]; sesid
0x18006c53c  call    cs:__imp_JetPrepareUpdate
0x18006c542  mov     esi, eax
0x18006c544  test    eax, eax
0x18006c546  jz      short loc_18006C5A7
0x18006c548  mov     rdx, [rbx]
0x18006c54b  mov     rcx, rbx
0x18006c54e  mov     rax, [rdx+30h]
0x18006c552  mov     edx, esi
0x18006c554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c559  mov     edi, eax
0x18006c55b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c562  lea     rbx, WPP_GLOBAL_Control
0x18006c569  cmp     rcx, rbx
0x18006c56c  jz      loc_18006C6A6
0x18006c572  test    [rcx+6Ch], r15b
0x18006c576  jz      loc_18006C67D
0x18006c57c  cmp     [rcx+69h], r13b
0x18006c580  jb      loc_18006C67D
0x18006c586  mov     edx, 117h
0x18006c58b  mov     rcx, [rcx+60h]
0x18006c58f  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x18006c596  mov     r9d, esi
0x18006c599  mov     dword ptr [rsp+0B0h+pcbActual], eax
0x18006c59d  call    WPP_SF_Dd
0x18006c5a2  jmp     loc_18006C676
0x18006c5a7  mov     r8, [rbx+190h]; psetcolumn
0x18006c5ae  mov     r9d, 12h; csetcolumn
0x18006c5b4  mov     rdx, [rbx+1F0h]; tableid
0x18006c5bb  mov     rcx, [rbx+178h]; sesid
0x18006c5c2  call    cs:__imp_JetSetColumns
0x18006c5c8  mov     esi, eax
0x18006c5ca  test    eax, eax
0x18006c5cc  jz      short loc_18006C60B
0x18006c5ce  mov     rcx, [rbx]
0x18006c5d1  mov     edx, esi
0x18006c5d3  mov     rax, [rcx+30h]
0x18006c5d7  mov     rcx, rbx
0x18006c5da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c5df  mov     edi, eax
0x18006c5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c5e8  lea     rbx, WPP_GLOBAL_Control
0x18006c5ef  cmp     rcx, rbx
0x18006c5f2  jz      loc_18006C6A6
0x18006c5f8  test    [rcx+6Ch], r15b
0x18006c5fc  jz      short loc_18006C67D
0x18006c5fe  cmp     [rcx+69h], r13b
0x18006c602  jb      short loc_18006C67D
0x18006c604  mov     edx, 118h
0x18006c609  jmp     short loc_18006C58B
0x18006c60b  mov     rdx, [rbx+1F0h]; tableid
0x18006c612  xor     r9d, r9d; cbBookmark
0x18006c615  mov     rcx, [rbx+178h]; sesid
0x18006c61c  xor     r8d, r8d; pvBookmark
0x18006c61f  mov     edi, r14d
0x18006c622  mov     [rsp+0B0h+pcbActual], r14; pcbActual
0x18006c627  call    cs:__imp_JetUpdate
0x18006c62d  mov     esi, eax
0x18006c62f  test    eax, eax
0x18006c631  jz      short loc_18006C66F
0x18006c633  mov     rcx, [rbx]
0x18006c636  mov     edx, esi
0x18006c638  mov     rax, [rcx+30h]
0x18006c63c  mov     rcx, rbx
0x18006c63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c644  mov     edi, eax
0x18006c646  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c64d  lea     rbx, WPP_GLOBAL_Control
0x18006c654  cmp     rcx, rbx
0x18006c657  jz      short loc_18006C6A6
0x18006c659  test    [rcx+6Ch], r15b
  ... truncated ...
```
