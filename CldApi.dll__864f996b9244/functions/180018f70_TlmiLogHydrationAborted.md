# TlmiLogHydrationAborted

- ea: `0x180018f70`
- end: `0x18001937b`
- name: `TlmiLogHydrationAborted`
- size: `1035`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011e18`

## callees

- `0x180001070`
- `0x180001a80`
- `0x180018f70`
- `0x180019e70`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001934a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001934a`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180018ffa`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180018ffa`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180018fd6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180018fd6`
- `AEPIC!PicFreeFileInfo` at `0x18001935a`
- `AEPIC!PicFreeFileInfo` at `0x18001935a`
- `AEPIC!PicRetrieveFileInfo` at `0x180019019`
- `AEPIC!PicRetrieveFileInfo` at `0x180019019`

## pseudocode

```c
void __fastcall TlmiLogHydrationAborted(__int64 a1)
{
  HANDLE v2; // rax
  void *v3; // rdi
  int v4; // ecx
  __int64 v5; // rax
  const WCHAR *v6; // r8
  __int64 v7; // rdx
  int v8; // edx
  const WCHAR *v9; // rdx
  __int64 v10; // r8
  int v11; // r8d
  const WCHAR *v12; // rdx
  __int64 v13; // r8
  int v14; // r8d
  const WCHAR *v15; // rdx
  __int64 v16; // r8
  int v17; // r8d
  const WCHAR *v18; // rdx
  __int64 v19; // r8
  int v20; // r8d
  const WCHAR *v21; // rdx
  __int64 v22; // r8
  int v23; // r8d
  const WCHAR *v24; // rdx
  __int64 v25; // r8
  int v26; // r8d
  const WCHAR *v27; // rdx
  __int64 v28; // r8
  int v29; // r8d
  const WCHAR *v30; // rdx
  __int64 v31; // r8
  int v32; // r8d
  const WCHAR *v33; // rdx
  DWORD dwSize; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+34h] [rbp-CCh] BYREF
  const WCHAR **v36; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v37; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v42; // [rsp+80h] [rbp-80h]
  __int64 v43; // [rsp+88h] [rbp-78h]
  _DWORD *v44; // [rsp+90h] [rbp-70h]
  __int64 v45; // [rsp+98h] [rbp-68h]
  WCHAR *v46; // [rsp+A0h] [rbp-60h]
  _DWORD v47[2]; // [rsp+A8h] [rbp-58h] BYREF
  const WCHAR *v48; // [rsp+B0h] [rbp-50h]
  int v49; // [rsp+B8h] [rbp-48h]
  int v50; // [rsp+BCh] [rbp-44h]
  const WCHAR *v51; // [rsp+C0h] [rbp-40h]
  int v52; // [rsp+C8h] [rbp-38h]
  int v53; // [rsp+CCh] [rbp-34h]
  const WCHAR *v54; // [rsp+D0h] [rbp-30h]
  int v55; // [rsp+D8h] [rbp-28h]
  int v56; // [rsp+DCh] [rbp-24h]
  const WCHAR *v57; // [rsp+E0h] [rbp-20h]
  int v58; // [rsp+E8h] [rbp-18h]
  int v59; // [rsp+ECh] [rbp-14h]
  const WCHAR *v60; // [rsp+F0h] [rbp-10h]
  int v61; // [rsp+F8h] [rbp-8h]
  int v62; // [rsp+FCh] [rbp-4h]
  const WCHAR *v63; // [rsp+100h] [rbp+0h]
  int v64; // [rsp+108h] [rbp+8h]
  int v65; // [rsp+10Ch] [rbp+Ch]
  const WCHAR *v66; // [rsp+110h] [rbp+10h]
  int v67; // [rsp+118h] [rbp+18h]
  int v68; // [rsp+11Ch] [rbp+1Ch]
  const WCHAR *v69; // [rsp+120h] [rbp+20h]
  int v70; // [rsp+128h] [rbp+28h]
  int v71; // [rsp+12Ch] [rbp+2Ch]
  const WCHAR *v72; // [rsp+130h] [rbp+30h]
  int v73; // [rsp+138h] [rbp+38h]
  int v74; // [rsp+13Ch] [rbp+3Ch]
  const WCHAR *v75; // [rsp+140h] [rbp+40h]
  int v76; // [rsp+148h] [rbp+48h]
  int v77; // [rsp+14Ch] [rbp+4Ch]
  __int64 *v78; // [rsp+150h] [rbp+50h]
  __int64 v79; // [rsp+158h] [rbp+58h]
  __int64 *v80; // [rsp+160h] [rbp+60h]
  __int64 v81; // [rsp+168h] [rbp+68h]
  int *v82; // [rsp+170h] [rbp+70h]
  __int64 v83; // [rsp+178h] [rbp+78h]
  __int64 *v84; // [rsp+180h] [rbp+80h]
  __int64 v85; // [rsp+188h] [rbp+88h]
  WCHAR ExeName[264]; // [rsp+190h] [rbp+90h] BYREF

  dwSize = 261;
  v36 = 0;
  if ( byte_180028930 && !NtCurrentPeb()->Ldr->ShutdownInProgress )
  {
    v2 = OpenProcess(0x1000u, 0, *(_DWORD *)(a1 + 16));
    v3 = v2;
    if ( v2 )
    {
      if ( QueryFullProcessImageNameW(v2, 1u, ExeName, &dwSize) )
      {
        if ( (int)PicRetrieveFileInfo(ExeName, 256, &v36) >= 0 )
        {
          TlmiRemoveUsername(ExeName);
          if ( (unsigned int)dword_1800281A0 > 5
            && (qword_1800281B0 & 0x400000000000LL) != 0
            && (qword_1800281B8 & 0x400000000000LL) == qword_1800281B8 )
          {
            v4 = 2;
            v37 = *(int *)(a1 + 20);
            v42 = &v37;
            v44 = v47;
            v46 = ExeName;
            v43 = 8;
            v47[0] = 2 * (unsigned __int16)dwSize;
            v5 = -1;
            v45 = 2;
            v47[1] = 0;
            v6 = v36[9];
            if ( v6 )
            {
              v7 = -1;
              do
                ++v7;
              while ( v6[v7] );
              v8 = 2 * v7 + 2;
            }
            else
            {
              v6 = &SourceString;
              v8 = 2;
            }
            v48 = v6;
            v49 = v8;
            v50 = 0;
            v9 = v36[4];
            if ( v9 )
            {
              v10 = -1;
              do
                ++v10;
              while ( v9[v10] );
              v11 = 2 * v10 + 2;
            }
            else
            {
              v9 = &SourceString;
              v11 = 2;
            }
            v51 = v9;
            v52 = v11;
            v53 = 0;
            v12 = v36[7];
            if ( v12 )
            {
              v13 = -1;
              do
                ++v13;
              while ( v12[v13] );
              v14 = 2 * v13 + 2;
            }
            else
            {
              v12 = &SourceString;
              v14 = 2;
            }
            v54 = v12;
            v55 = v14;
            v56 = 0;
            v15 = v36[2];
            if ( v15 )
            {
              v16 = -1;
              do
                ++v16;
              while ( v15[v16] );
              v17 = 2 * v16 + 2;
            }
            else
            {
              v15 = &SourceString;
              v17 = 2;
            }
            v57 = v15;
            v58 = v17;
            v59 = 0;
            v18 = *v36;
            if ( *v36 )
            {
              v19 = -1;
              do
                ++v19;
              while ( v18[v19] );
              v20 = 2 * v19 + 2;
            }
            else
            {
              v18 = &SourceString;
              v20 = 2;
            }
            v60 = v18;
            v61 = v20;
            v62 = 0;
            v21 = v36[3];
            if ( v21 )
            {
              v22 = -1;
              do
                ++v22;
              while ( v21[v22] );
              v23 = 2 * v22 + 2;
            }
            else
            {
              v21 = &SourceString;
              v23 = 2;
            }
            v63 = v21;
            v64 = v23;
            v65 = 0;
            v24 = v36[6];
            if ( v24 )
            {
              v25 = -1;
              do
                ++v25;
              while ( v24[v25] );
              v26 = 2 * v25 + 2;
            }
            else
            {
              v24 = &SourceString;
              v26 = 2;
            }
            v66 = v24;
            v67 = v26;
            v68 = 0;
            v27 = v36[8];
            if ( v27 )
            {
              v28 = -1;
              do
                ++v28;
              while ( v27[v28] );
              v29 = 2 * v28 + 2;
            }
            else
            {
              v27 = &SourceString;
              v29 = 2;
            }
            v69 = v27;
            v70 = v29;
            v71 = 0;
            v30 = v36[1];
            if ( v30 )
            {
              v31 = -1;
              do
                ++v31;
              while ( v30[v31] );
              v32 = 2 * v31 + 2;
            }
            else
            {
              v30 = &SourceString;
              v32 = 2;
            }
            v72 = v30;
            v73 = v32;
            v74 = 0;
            v33 = v36[5];
            if ( v33 )
            {
              do
                ++v5;
              while ( v33[v5] );
              v4 = 2 * v5 + 2;
            }
            else
            {
              v33 = &SourceString;
            }
            v38 = (unsigned int)dword_180028B78;
            v75 = v33;
            v78 = &v38;
            v39 = qword_180028B70;
            v80 = &v39;
            v35 = dword_180028B7C;
            v82 = &v35;
            v84 = &v40;
            v76 = v4;
            v77 = 0;
            v79 = 8;
            v81 = 8;
            v83 = 4;
            v40 = 0x1000000;
            v85 = 8;
            tlgWriteTransfer_EventWriteTransfer(
              (__int64)&dword_1800281A0,
              (unsigned __int8 *)byte_18002198F,
              0,
              0,
              0x13u,
              &v41);
          }
        }
      }
      CloseHandle(v3);
    }
    if ( v36 )
      PicFreeFileInfo();
  }
}

```

## disassembly

```asm
0x180018f70  push    rbp
0x180018f72  push    rbx
0x180018f73  push    rsi
0x180018f74  push    rdi
0x180018f75  lea     rbp, [rsp-2B8h]
0x180018f7d  sub     rsp, 3B8h
0x180018f84  mov     rax, cs:__security_cookie
0x180018f8b  xor     rax, rsp
0x180018f8e  mov     [rbp+2D0h+var_30], rax
0x180018f95  xor     esi, esi
0x180018f97  mov     [rsp+3D0h+dwSize], 105h
0x180018f9f  cmp     cs:byte_180028930, sil
0x180018fa6  mov     rbx, rcx
0x180018fa9  mov     [rsp+3D0h+var_398], rsi
0x180018fae  jz      loc_180019360
0x180018fb4  mov     rax, gs:60h
0x180018fbd  mov     rdx, [rax+18h]
0x180018fc1  cmp     [rdx+48h], sil
0x180018fc5  jnz     loc_180019360
0x180018fcb  mov     r8d, [rcx+10h]; dwProcessId
0x180018fcf  xor     edx, edx; bInheritHandle
0x180018fd1  mov     ecx, 1000h; dwDesiredAccess
0x180018fd6  call    cs:__imp_OpenProcess
0x180018fdc  mov     rdi, rax
0x180018fdf  test    rax, rax
0x180018fe2  jz      loc_180019350
0x180018fe8  lea     r9, [rsp+3D0h+dwSize]; lpdwSize
0x180018fed  mov     rcx, rax; hProcess
0x180018ff0  lea     r8, [rbp+2D0h+ExeName]; lpExeName
0x180018ff7  lea     edx, [rsi+1]; dwFlags
0x180018ffa  call    cs:__imp_QueryFullProcessImageNameW
0x180019000  test    eax, eax
0x180019002  jz      loc_180019347
0x180019008  lea     r8, [rsp+3D0h+var_398]
0x18001900d  mov     edx, 100h
0x180019012  lea     rcx, [rbp+2D0h+ExeName]
0x180019019  call    cs:__imp_PicRetrieveFileInfo
0x18001901f  test    eax, eax
0x180019021  js      loc_180019347
0x180019027  movzx   edx, word ptr [rsp+3D0h+dwSize]
0x18001902c  lea     rcx, [rbp+2D0h+ExeName]
0x180019033  add     dx, dx
0x180019036  call    TlmiRemoveUsername
0x18001903b  mov     eax, cs:dword_1800281A0
0x180019041  cmp     eax, 5
0x180019044  jbe     loc_180019347
0x18001904a  mov     rcx, cs:qword_1800281B8
0x180019051  mov     rdx, 400000000000h
0x18001905b  mov     rax, cs:qword_1800281B0
0x180019062  test    rdx, rax
0x180019065  jz      loc_180019347
0x18001906b  mov     rax, rcx
0x18001906e  and     rax, rdx
0x180019071  cmp     rax, rcx
0x180019074  jnz     loc_180019347
0x18001907a  movsxd  rax, dword ptr [rbx+14h]
0x18001907e  lea     ecx, [rsi+2]
0x180019081  mov     r9, [rsp+3D0h+var_398]
0x180019086  lea     r10, SourceString
0x18001908d  mov     [rsp+3D0h+var_390], rax
0x180019092  lea     rax, [rsp+3D0h+var_390]
0x180019097  mov     [rbp+2D0h+var_350], rax
0x18001909b  lea     rax, [rbp+2D0h+var_328]
0x18001909f  mov     [rbp+2D0h+var_340], rax
0x1800190a3  lea     rax, [rbp+2D0h+ExeName]
0x1800190aa  mov     [rbp+2D0h+var_330], rax
0x1800190ae  movzx   eax, word ptr [rsp+3D0h+dwSize]
0x1800190b3  add     eax, eax
0x1800190b5  mov     [rbp+2D0h+var_348], 8
0x1800190bd  mov     [rbp+2D0h+var_328], eax
0x1800190c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800190c4  mov     [rbp+2D0h+var_338], rcx
0x1800190c8  mov     [rbp+2D0h+var_324], esi
0x1800190cb  mov     r8, [r9+48h]
0x1800190cf  test    r8, r8
0x1800190d2  jz      short loc_1800190EA
0x1800190d4  mov     rdx, rax
0x1800190d7  inc     rdx
0x1800190da  cmp     [r8+rdx*2], si
0x1800190df  jnz     short loc_1800190D7
0x1800190e1  lea     edx, ds:2[rdx*2]
0x1800190e8  jmp     short loc_1800190EF
0x1800190ea  mov     r8, r10
0x1800190ed  mov     edx, ecx
0x1800190ef  mov     [rbp+2D0h+var_320], r8
0x1800190f3  mov     [rbp+2D0h+var_318], edx
0x1800190f6  mov     [rbp+2D0h+var_314], esi
0x1800190f9  mov     rdx, [r9+20h]
0x1800190fd  test    rdx, rdx
0x180019100  jz      short loc_180019119
0x180019102  mov     r8, rax
0x180019105  inc     r8
0x180019108  cmp     [rdx+r8*2], si
0x18001910d  jnz     short loc_180019105
0x18001910f  lea     r8d, ds:2[r8*2]
0x180019117  jmp     short loc_18001911F
0x180019119  mov     rdx, r10
0x18001911c  mov     r8d, ecx
0x18001911f  mov     [rbp+2D0h+var_310], rdx
0x180019123  mov     [rbp+2D0h+var_308], r8d
0x180019127  mov     [rbp+2D0h+var_304], esi
0x18001912a  mov     rdx, [r9+38h]
0x18001912e  test    rdx, rdx
0x180019131  jz      short loc_18001914A
0x180019133  mov     r8, rax
0x180019136  inc     r8
0x180019139  cmp     [rdx+r8*2], si
0x18001913e  jnz     short loc_180019136
0x180019140  lea     r8d, ds:2[r8*2]
0x180019148  jmp     short loc_180019150
0x18001914a  mov     rdx, r10
0x18001914d  mov     r8d, ecx
0x180019150  mov     [rbp+2D0h+var_300], rdx
0x180019154  mov     [rbp+2D0h+var_2F8], r8d
0x180019158  mov     [rbp+2D0h+var_2F4], esi
0x18001915b  mov     rdx, [r9+10h]
0x18001915f  test    rdx, rdx
0x180019162  jz      short loc_18001917B
0x180019164  mov     r8, rax
0x180019167  inc     r8
0x18001916a  cmp     [rdx+r8*2], si
0x18001916f  jnz     short loc_180019167
0x180019171  lea     r8d, ds:2[r8*2]
0x180019179  jmp     short loc_180019181
0x18001917b  mov     rdx, r10
0x18001917e  mov     r8d, ecx
0x180019181  mov     [rbp+2D0h+var_2F0], rdx
0x180019185  mov     [rbp+2D0h+var_2E8], r8d
0x180019189  mov     [rbp+2D0h+var_2E4], esi
0x18001918c  mov     rdx, [r9]
0x18001918f  test    rdx, rdx
0x180019192  jz      short loc_1800191AB
0x180019194  mov     r8, rax
0x180019197  inc     r8
0x18001919a  cmp     [rdx+r8*2], si
0x18001919f  jnz     short loc_180019197
0x1800191a1  lea     r8d, ds:2[r8*2]
0x1800191a9  jmp     short loc_1800191B1
0x1800191ab  mov     rdx, r10
0x1800191ae  mov     r8d, ecx
0x1800191b1  mov     [rbp+2D0h+var_2E0], rdx
0x1800191b5  mov     [rbp+2D0h+var_2D8], r8d
0x1800191b9  mov     [rbp+2D0h+var_2D4], esi
0x1800191bc  mov     rdx, [r9+18h]
0x1800191c0  test    rdx, rdx
0x1800191c3  jz      short loc_1800191DC
0x1800191c5  mov     r8, rax
0x1800191c8  inc     r8
0x1800191cb  cmp     [rdx+r8*2], si
0x1800191d0  jnz     short loc_1800191C8
0x1800191d2  lea     r8d, ds:2[r8*2]
0x1800191da  jmp     short loc_1800191E2
0x1800191dc  mov     rdx, r10
0x1800191df  mov     r8d, ecx
0x1800191e2  mov     [rbp+2D0h+var_2D0], rdx
0x1800191e6  mov     [rbp+2D0h+var_2C8], r8d
0x1800191ea  mov     [rbp+2D0h+var_2C4], esi
0x1800191ed  mov     rdx, [r9+30h]
0x1800191f1  test    rdx, rdx
0x1800191f4  jz      short loc_18001920D
0x1800191f6  mov     r8, rax
0x1800191f9  inc     r8
0x1800191fc  cmp     [rdx+r8*2], si
0x180019201  jnz     short loc_1800191F9
0x180019203  lea     r8d, ds:2[r8*2]
0x18001920b  jmp     short loc_180019213
0x18001920d  mov     rdx, r10
0x180019210  mov     r8d, ecx
0x180019213  mov     [rbp+2D0h+var_2C0], rdx
0x180019217  mov     [rbp+2D0h+var_2B8], r8d
0x18001921b  mov     [rbp+2D0h+var_2B4], esi
0x18001921e  mov     rdx, [r9+40h]
0x180019222  test    rdx, rdx
0x180019225  jz      short loc_18001923E
0x180019227  mov     r8, rax
0x18001922a  inc     r8
0x18001922d  cmp     [rdx+r8*2], si
0x180019232  jnz     short loc_18001922A
0x180019234  lea     r8d, ds:2[r8*2]
0x18001923c  jmp     short loc_180019244
0x18001923e  mov     rdx, r10
0x180019241  mov     r8d, ecx
0x180019244  mov     [rbp+2D0h+var_2B0], rdx
0x180019248  mov     [rbp+2D0h+var_2A8], r8d
0x18001924c  mov     [rbp+2D0h+var_2A4], esi
0x18001924f  mov     rdx, [r9+8]
0x180019253  test    rdx, rdx
0x180019256  jz      short loc_18001926F
0x180019258  mov     r8, rax
0x18001925b  inc     r8
0x18001925e  cmp     [rdx+r8*2], si
0x180019263  jnz     short loc_18001925B
0x180019265  lea     r8d, ds:2[r8*2]
0x18001926d  jmp     short loc_180019275
0x18001926f  mov     rdx, r10
0x180019272  mov     r8d, ecx
0x180019275  mov     [rbp+2D0h+var_2A0], rdx
0x180019279  mov     [rbp+2D0h+var_298], r8d
0x18001927d  mov     [rbp+2D0h+var_294], esi
0x180019280  mov     rdx, [r9+28h]
0x180019284  test    rdx, rdx
0x180019287  jz      short loc_18001929B
0x180019289  inc     rax
0x18001928c  cmp     [rdx+rax*2], si
0x180019290  jnz     short loc_180019289
0x180019292  lea     ecx, ds:2[rax*2]
0x180019299  jmp     short loc_18001929E
0x18001929b  mov     rdx, r10
0x18001929e  mov     eax, cs:dword_180028B78
0x1800192a4  xor     r9d, r9d
0x1800192a7  mov     [rsp+3D0h+var_388], rax
0x1800192ac  xor     r8d, r8d
0x1800192af  lea     rax, [rsp+3D0h+var_388]
0x1800192b4  mov     [rbp+2D0h+var_290], rdx
0x1800192b8  mov     [rbp+2D0h+var_280], rax
0x1800192bc  lea     rdx, byte_18002198F
0x1800192c3  mov     rax, cs:qword_180028B70
0x1800192ca  mov     [rsp+3D0h+var_380], rax
0x1800192cf  lea     rax, [rsp+3D0h+var_380]
0x1800192d4  mov     [rbp+2D0h+var_270], rax
0x1800192d8  mov     eax, cs:dword_180028B7C
0x1800192de  mov     [rsp+3D0h+var_39C], eax
0x1800192e2  lea     rax, [rsp+3D0h+var_39C]
0x1800192e7  mov     [rbp+2D0h+var_260], rax
0x1800192eb  lea     rax, [rsp+3D0h+var_378]
0x1800192f0  mov     [rbp+2D0h+var_250], rax
0x1800192f7  lea     rax, [rsp+3D0h+var_370]
0x1800192fc  mov     [rbp+2D0h+var_288], ecx
0x1800192ff  lea     rcx, dword_1800281A0
0x180019306  mov     [rsp+3D0h+var_3A8], rax
0x18001930b  mov     [rsp+3D0h+var_3B0], 13h
0x180019313  mov     [rbp+2D0h+var_284], esi
0x180019316  mov     [rbp+2D0h+var_278], 8
0x18001931e  mov     [rbp+2D0h+var_268], 8
0x180019326  mov     [rbp+2D0h+var_258], 4
0x18001932e  mov     [rsp+3D0h+var_378], 1000000h
0x180019337  mov     [rbp+2D0h+var_248], 8
0x180019342  call    _tlgWriteTransfer_EventWriteTransfer
0x180019347  mov     rcx, rdi; hObject
0x18001934a  call    cs:__imp_CloseHandle
0x180019350  mov     rcx, [rsp+3D0h+var_398]
0x180019355  test    rcx, rcx
0x180019358  jz      short loc_180019360
0x18001935a  call    cs:__imp_PicFreeFileInfo
0x180019360  mov     rcx, [rbp+2D0h+var_30]
0x180019367  xor     rcx, rsp; StackCookie
0x18001936a  call    __security_check_cookie
0x18001936f  add     rsp, 3B8h
0x180019376  pop     rdi
0x180019377  pop     rsi
0x180019378  pop     rbx
0x180019379  pop     rbp
0x18001937a  retn
```
