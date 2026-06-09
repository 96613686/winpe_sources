# sub_140BB7FE0

- ea: `0x140bb7fe0`
- end: `0x140bb84d6`
- name: `sub_140BB7FE0`
- size: `1270`
- prototype: ``
- caller_count: `8`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x140a5dd20`
- `0x140bb7fe0`
- `0x140cffae0`
- `0x1416c11c0`
- `0x143628490`
- `0x14362e3b0`
- `0x143631af0`
- `0x143633f00`

## callees

- `0x14007fb80`
- `0x14007fda0`
- `0x140183210`
- `0x1408d2bb0`
- `0x1408d6570`
- `0x140aaa618`
- `0x140aca1e0`
- `0x140b2d310`
- `0x140bb7fe0`
- `0x140d69720`
- `0x140f0eedc`
- `0x14122bfdc`
- `0x14139f05c`
- `0x1436b4fd9`

## import_xrefs

- `OLEAUT32!VariantInit` at `0x140bb8020`
- `OLEAUT32!VariantInit` at `0x140bb8020`
- `OLEAUT32!VariantClear` at `0x140bb8080`
- `OLEAUT32!VariantClear` at `0x140bb80c0`
- `OLEAUT32!VariantClear` at `0x140bb81e7`
- `OLEAUT32!VariantClear` at `0x140bb8213`
- `OLEAUT32!VariantClear` at `0x140bb8299`
- `OLEAUT32!VariantClear` at `0x140bb834b`
- `OLEAUT32!VariantClear` at `0x140bb83ab`
- `OLEAUT32!VariantClear` at `0x140bb83ee`
- `OLEAUT32!VariantClear` at `0x140bb8080`
- `OLEAUT32!VariantClear` at `0x140bb80c0`
- `OLEAUT32!VariantClear` at `0x140bb81e7`
- `OLEAUT32!VariantClear` at `0x140bb8213`
- `OLEAUT32!VariantClear` at `0x140bb8299`
- `OLEAUT32!VariantClear` at `0x140bb834b`
- `OLEAUT32!VariantClear` at `0x140bb83ab`
- `OLEAUT32!VariantClear` at `0x140bb83ee`
- `OLEAUT32!SafeArrayCreate` at `0x140bb8115`
- `OLEAUT32!SafeArrayCreate` at `0x140bb8115`
- `OLEAUT32!SafeArrayAccessData` at `0x140bb8142`
- `OLEAUT32!SafeArrayAccessData` at `0x140bb8142`
- `OLEAUT32!SafeArrayUnaccessData` at `0x140bb8165`
- `OLEAUT32!SafeArrayUnaccessData` at `0x140bb824f`
- `OLEAUT32!SafeArrayUnaccessData` at `0x140bb8165`
- `OLEAUT32!SafeArrayUnaccessData` at `0x140bb824f`
- `Mso20Win32Client!__imp_Mso20Win32Client_7228` at `0x140bb8151`
- `Mso20Win32Client!__imp_Mso20Win32Client_7228` at `0x140bb8151`
- `Mso20Win32Client!Mso20Win32Client_12657` at `0x140bb83e2`
- `Mso20Win32Client!Mso20Win32Client_12657` at `0x140bb83e2`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb8091`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb80d1`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb8200`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb8224`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb82ab`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb8360`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb83c0`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb8400`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb8091`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb80d1`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb8200`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb8224`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb82ab`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb8360`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb83c0`
- `Mso20Win32Client!Mso20Win32Client_26547` at `0x140bb8400`
- `Mso20Win32Client!Mso20Win32Client_44442` at `0x140bb8340`
- `Mso20Win32Client!Mso20Win32Client_44442` at `0x140bb8340`
- `Mso20Win32Client!Mso20Win32Client_52971` at `0x140bb83a0`
- `Mso20Win32Client!Mso20Win32Client_52971` at `0x140bb83a0`
- `Mso20Win32Client!Mso20Win32Client_57205` at `0x140bb8034`
- `Mso20Win32Client!Mso20Win32Client_57205` at `0x140bb8034`
- `Mso20Win32Client!Mso20Win32Client_58193` at `0x140bb8464`
- `Mso20Win32Client!Mso20Win32Client_58193` at `0x140bb8464`
- `Mso20Win32Client!Mso20Win32Client_61346` at `0x140bb830d`
- `Mso20Win32Client!Mso20Win32Client_61346` at `0x140bb830d`

## pseudocode

```c
VARIANTARG *__fastcall sub_140BB7FE0(VARIANTARG *a1, _QWORD *a2)
{
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  HRESULT v9; // eax
  HRESULT v10; // eax
  SAFEARRAY *v11; // rax
  SAFEARRAY *v12; // r14
  __int64 v13; // rbx
  __int64 v14; // rdi
  __int64 v15; // r15
  __int64 v16; // rax
  __int128 v17; // xmm1
  __int64 v18; // xmm0_8
  char *v19; // rax
  HRESULT v20; // eax
  HRESULT v21; // eax
  __int64 v22; // rax
  __int64 v23; // rbx
  HRESULT v24; // eax
  _QWORD *v25; // rdx
  unsigned __int8 v26; // bl
  HRESULT v27; // eax
  LONG v28; // ebx
  HRESULT v29; // eax
  double v30; // xmm6_8
  HRESULT v31; // eax
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp-D0h] BYREF
  int v34; // [rsp+38h] [rbp-C8h]
  void *ppvData[2]; // [rsp+40h] [rbp-C0h] BYREF
  SAFEARRAY *v36; // [rsp+50h] [rbp-B0h]
  VARIANTARG *v37; // [rsp+58h] [rbp-A8h]
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v39; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h]
  _BYTE v41[8]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v42; // [rsp+90h] [rbp-70h]
  _BYTE pExceptionObject[144]; // [rsp+B0h] [rbp-50h] BYREF

  v37 = a1;
  VariantInit(a1);
  v34 = 1;
  v4 = Mso20Win32Client_57205(a2);
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            if ( v8 != 1 )
            {
              rgsabound.cElements = -2147024809;
              sub_14139F05C(36467780, 1251, 15, (unsigned int)L"RichApiException 0x%x", (__int64)&rgsabound);
              sub_14122BFDC(pExceptionObject, rgsabound.cElements);
              throw (OfficeExtension::ServerRuntime::RichApiException *)pExceptionObject;
            }
            v9 = VariantClear(a1);
            if ( v9 < 0 )
            {
              Mso20Win32Client_26547((unsigned int)v9, 528089229);
              __debugbreak();
            }
            if ( a1 )
            {
              *(_OWORD *)&a1->vt = 0;
              a1->pRecInfo = 0;
            }
          }
          else
          {
            v10 = VariantClear(a1);
            if ( v10 < 0 )
            {
              Mso20Win32Client_26547((unsigned int)v10, 528089229);
              __debugbreak();
            }
            if ( a1 )
            {
              *(_OWORD *)&a1->vt = 0;
              a1->pRecInfo = 0;
            }
            rgsabound.cElements = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 160LL))(*a2);
            rgsabound.lLbound = 0;
            v11 = SafeArrayCreate(0xCu, 1u, &rgsabound);
            v12 = v11;
            v36 = v11;
            if ( !v11 )
            {
              Mso20Win32Client_58193(36467779, 1251, 15, L"RichApiException false");
              sub_14122BFDC(pExceptionObject, 2147942414LL);
              throw (OfficeExtension::ServerRuntime::RichApiException *)pExceptionObject;
            }
            ppvData[0] = v11;
            ppvData[1] = 0;
            if ( SafeArrayAccessData(v11, &ppvData[1]) < 0 )
            {
              Mso20Win32Client_7228(528089233);
              if ( ppvData[0] )
                SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
              *(_OWORD *)ppvData = 0;
            }
            v13 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 8LL))(*a2);
            v14 = *(_QWORD *)((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 8LL))(*a2) + 8);
            v15 = 0;
            while ( v13 != v14 )
            {
              sub_140BB7FE0(&pvarg, v13 + 8);
              v16 = sub_140AAA618(&pvarg, &v39);
              v17 = *(_OWORD *)v16;
              v18 = *(_QWORD *)(v16 + 16);
              v19 = (char *)ppvData[1];
              *(_OWORD *)((char *)ppvData[1] + v15) = v17;
              *(_QWORD *)&v19[v15 + 16] = v18;
              v15 += 24;
              v20 = VariantClear(&pvarg);
              if ( v20 < 0 )
              {
                Mso20Win32Client_26547((unsigned int)v20, 528089229);
                __debugbreak();
              }
              v13 += 16;
            }
            v36 = 0;
            v21 = VariantClear(a1);
            if ( v21 < 0 )
            {
              Mso20Win32Client_26547((unsigned int)v21, 528089229);
              __debugbreak();
            }
            if ( a1 )
            {
              *(_OWORD *)&a1->vt = 0;
              a1->pRecInfo = 0;
            }
            a1->vt = 8204;
            a1->llVal = (LONGLONG)v12;
            if ( ppvData[0] )
              SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
          }
        }
        else
        {
          sub_140F0EEDC(&v39, a2);
          v22 = sub_14007FDA0(0x50u);
          if ( v22 )
            v23 = sub_140B2D310(v22, &v39);
          else
            v23 = 0;
          if ( v23 )
            _InterlockedAdd((volatile signed __int32 *)(v23 + 72), 1u);
          v24 = VariantClear(a1);
          if ( v24 < 0 )
          {
            Mso20Win32Client_26547((unsigned int)v24, 528089229);
            __debugbreak();
          }
          if ( a1 )
          {
            *(_OWORD *)&a1->vt = 0;
            a1->pRecInfo = 0;
          }
          a1->vt = 13;
          a1->llVal = v23;
          sub_140183210(v41);
          if ( v40 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 168LL))(v40, 1);
        }
      }
      else
      {
        Mso20Win32Client_61346(a2, &v39);
        v25 = &v39;
        if ( v42 > 7 )
          v25 = v39;
        sub_140ACA1E0(a1, v25);
        sub_14007FB80(&v39);
      }
    }
    else
    {
      v26 = Mso20Win32Client_44442(a2);
      v27 = VariantClear(a1);
      if ( v27 < 0 )
      {
        Mso20Win32Client_26547((unsigned int)v27, 528089229);
        __debugbreak();
      }
      if ( a1 )
      {
        *(_OWORD *)&a1->vt = 0;
        a1->pRecInfo = 0;
      }
      a1->vt = 11;
      a1->iVal = (v26 ^ 1) - 1;
    }
  }
  else if ( (unsigned __int8)sub_140D69720(a2) )
  {
    v28 = Mso20Win32Client_52971(a2);
    v29 = VariantClear(a1);
    if ( v29 < 0 )
    {
      Mso20Win32Client_26547((unsigned int)v29, 528089229);
      __debugbreak();
    }
    if ( a1 )
    {
      *(_OWORD *)&a1->vt = 0;
      a1->pRecInfo = 0;
    }
    a1->vt = 3;
    a1->lVal = v28;
  }
  else
  {
    v30 = Mso20Win32Client_12657(a2);
    v31 = VariantClear(a1);
    if ( v31 < 0 )
    {
      Mso20Win32Client_26547((unsigned int)v31, 528089229);
      __debugbreak();
    }
    if ( a1 )
    {
      *(_OWORD *)&a1->vt = 0;
      a1->pRecInfo = 0;
    }
    a1->vt = 5;
    a1->dblVal = v30;
  }
  return a1;
}

```

## disassembly

```asm
0x140bb7fe0  mov     rax, rsp
0x140bb7fe3  mov     [rax+18h], rbx
0x140bb7fe7  push    rbp
0x140bb7fe8  push    rsi
0x140bb7fe9  push    rdi
0x140bb7fea  push    r14
0x140bb7fec  push    r15
0x140bb7fee  lea     rbp, [rsp-60h]
0x140bb7ff3  sub     rsp, 160h
0x140bb7ffa  movaps  xmmword ptr [rax-38h], xmm6
0x140bb7ffe  mov     rax, cs:__security_cookie
0x140bb8005  xor     rax, rsp
0x140bb8008  mov     [rbp+80h+var_40], rax
0x140bb800c  mov     rdi, rdx
0x140bb800f  mov     rsi, rcx
0x140bb8012  mov     [rsp+180h+var_128], rcx
0x140bb8017  mov     [rsp+180h+var_148], 0
0x140bb801f  nop
0x140bb8020  call    cs:VariantInit
0x140bb8026  mov     r14d, 1
0x140bb802c  mov     [rsp+180h+var_148], r14d
0x140bb8031  mov     rcx, rdi
0x140bb8034  call    cs:Mso20Win32Client_57205
0x140bb803a  mov     ecx, eax
0x140bb8040  test    eax, eax
0x140bb8042  jz      loc_140BB8390
0x140bb8048  sub     ecx, r14d
0x140bb804b  jz      loc_140BB833C
0x140bb8051  sub     ecx, r14d
0x140bb8054  jz      loc_140BB8305
0x140bb805a  nop     word ptr [rax+rax+00h]
0x140bb8060  sub     ecx, r14d
0x140bb8063  jz      loc_140BB825B
0x140bb8069  sub     ecx, r14d
0x140bb806c  jz      short loc_140BB80BA
0x140bb806e  cmp     ecx, r14d
0x140bb8071  jnz     loc_140BB8489
0x140bb8077  mov     rcx, rsi; pvarg
0x140bb8080  call    cs:VariantClear
0x140bb8086  test    eax, eax
0x140bb8088  jns     short loc_140BB8098
0x140bb808a  mov     edx, 1F7A008Dh
0x140bb808f  mov     ecx, eax
0x140bb8091  call    cs:Mso20Win32Client_26547
0x140bb8097  int     3; Trap to Debugger
0x140bb8098  nop     dword ptr [rax+rax+00000000h]
0x140bb80a0  test    rsi, rsi
0x140bb80a3  jz      loc_140BB8422
0x140bb80a9  xorps   xmm0, xmm0
0x140bb80ac  xor     eax, eax
0x140bb80ae  movups  xmmword ptr [rsi], xmm0
0x140bb80b1  mov     [rsi+10h], rax
0x140bb80b5  jmp     loc_140BB8422
0x140bb80ba  mov     rcx, rsi; pvarg
0x140bb80c0  call    cs:VariantClear
0x140bb80c6  test    eax, eax
0x140bb80c8  jns     short loc_140BB80D8
0x140bb80ca  mov     edx, 1F7A008Dh
0x140bb80cf  mov     ecx, eax
0x140bb80d1  call    cs:Mso20Win32Client_26547
0x140bb80d7  int     3; Trap to Debugger
0x140bb80d8  test    rsi, rsi
0x140bb80db  jz      short loc_140BB80E9
0x140bb80dd  xorps   xmm0, xmm0
0x140bb80e0  xor     eax, eax
0x140bb80e2  movups  xmmword ptr [rsi], xmm0
0x140bb80e5  mov     [rsi+10h], rax
0x140bb80e9  mov     rcx, [rdi]
0x140bb80ec  mov     rax, [rcx]
0x140bb80ef  mov     rax, [rax+0A0h]
0x140bb80f6  call    cs:__guard_dispatch_icall_fptr
0x140bb80fc  mov     [rsp+180h+rgsabound.cElements], eax
0x140bb8100  mov     [rsp+180h+rgsabound.lLbound], 0
0x140bb8108  mov     ecx, 0Ch; vt
0x140bb810d  lea     r8, [rsp+180h+rgsabound]; rgsabound
0x140bb8112  mov     edx, r14d; cDims
0x140bb8115  call    cs:SafeArrayCreate
0x140bb811b  mov     r14, rax
0x140bb811e  mov     [rsp+180h+var_130], rax
0x140bb8123  test    rax, rax
0x140bb8126  jz      loc_140BB844D
0x140bb812c  mov     [rsp+180h+ppvData], rax
0x140bb8131  mov     [rsp+180h+ppvData+8], 0
0x140bb813a  lea     rdx, [rsp+180h+ppvData+8]; ppvData
0x140bb813f  mov     rcx, rax; psa
0x140bb8142  call    cs:SafeArrayAccessData
0x140bb8148  test    eax, eax
0x140bb814a  jns     short loc_140BB8174
0x140bb814c  mov     ecx, 1F7A0091h
0x140bb8151  call    cs:__imp_Mso20Win32Client_7228
0x140bb8157  mov     rcx, [rsp+40h]; psa
0x140bb8160  test    rcx, rcx
0x140bb8163  jz      short loc_140BB816B
0x140bb8165  call    cs:SafeArrayUnaccessData
0x140bb816b  xorps   xmm0, xmm0
0x140bb816e  movdqu  xmmword ptr [rsp+180h+ppvData], xmm0
0x140bb8174  mov     rcx, [rdi]
0x140bb8178  mov     rax, [rcx]
0x140bb817b  mov     rax, [rax+8]
0x140bb817f  nop
0x140bb8180  call    cs:__guard_dispatch_icall_fptr
0x140bb8186  mov     rbx, [rax]
0x140bb8189  mov     rcx, [rdi]
0x140bb818c  mov     rax, [rcx]
0x140bb818f  mov     rax, [rax+8]
0x140bb8193  call    cs:__guard_dispatch_icall_fptr
0x140bb8199  mov     rdi, [rax+8]
0x140bb819d  xor     r15d, r15d
0x140bb81a0  cmp     rbx, rdi
0x140bb81a3  jz      short loc_140BB8207
0x140bb81a5  lea     rdx, [rbx+8]
0x140bb81a9  lea     rcx, [rsp+180h+pvarg]
0x140bb81ae  call    sub_140BB7FE0
0x140bb81b3  lea     rdx, [rsp+78h]
0x140bb81bb  lea     rcx, [rsp+180h+pvarg]
0x140bb81c0  call    sub_140AAA618
0x140bb81c5  movups  xmm1, xmmword ptr [rax]
0x140bb81c8  movsd   xmm0, qword ptr [rax+10h]
0x140bb81cd  mov     rax, [rsp+180h+ppvData+8]
0x140bb81d2  movups  xmmword ptr [rax+r15], xmm1
0x140bb81d7  movsd   qword ptr [rax+r15+10h], xmm0
0x140bb81de  add     r15, 18h
0x140bb81e2  lea     rcx, [rsp+180h+pvarg]; pvarg
0x140bb81e7  call    cs:VariantClear
0x140bb81ed  test    eax, eax
0x140bb81ef  js      short loc_140BB81F7
0x140bb81f1  add     rbx, 10h
0x140bb81f5  jmp     short loc_140BB81A0
0x140bb81f7  mov     edx, 1F7A008Dh
0x140bb81fe  mov     ecx, eax
0x140bb8200  call    cs:Mso20Win32Client_26547
0x140bb8206  int     3; Trap to Debugger
0x140bb8207  mov     [rsp+180h+var_130], 0
0x140bb8210  mov     rcx, rsi; pvarg
0x140bb8213  call    cs:VariantClear
0x140bb8219  test    eax, eax
0x140bb821b  jns     short loc_140BB822B
0x140bb821d  mov     edx, 1F7A008Dh
0x140bb8222  mov     ecx, eax
0x140bb8224  call    cs:Mso20Win32Client_26547
0x140bb822a  int     3; Trap to Debugger
0x140bb822b  test    rsi, rsi
0x140bb822e  jz      short loc_140BB823C
0x140bb8230  xorps   xmm0, xmm0
0x140bb8233  xor     eax, eax
0x140bb8235  movups  xmmword ptr [rsi], xmm0
0x140bb8238  mov     [rsi+10h], rax
0x140bb823c  mov     word ptr [rsi], 200Ch
0x140bb8241  mov     [rsi+8], r14
0x140bb8245  mov     rcx, [rsp+180h+ppvData]; psa
0x140bb824a  test    rcx, rcx
0x140bb824d  jz      short loc_140BB8256
0x140bb824f  call    cs:SafeArrayUnaccessData
0x140bb8255  nop
0x140bb8256  jmp     loc_140BB8422
0x140bb825b  mov     rdx, rdi
0x140bb825e  lea     rcx, [rsp+180h+var_108]
0x140bb8263  call    sub_140F0EEDC
0x140bb8268  mov     ecx, 50h ; 'P'; Size
0x140bb826d  call    sub_14007FDA0
0x140bb8272  test    rax, rax
0x140bb8275  jz      short loc_140BB828A
0x140bb8277  lea     rdx, [rsp+78h]
0x140bb827d  mov     rcx, rax
0x140bb8280  call    sub_140B2D310
0x140bb8285  mov     rbx, rax
0x140bb8288  jmp     short loc_140BB828C
0x140bb828a  xor     ebx, ebx
0x140bb828c  test    rbx, rbx
0x140bb828f  jz      short loc_140BB8296
0x140bb8291  lock add [rbx+48h], r14d
0x140bb8296  mov     rcx, rsi; pvarg
0x140bb8299  call    cs:VariantClear
0x140bb829f  nop
0x140bb82a0  test    eax, eax
0x140bb82a2  jns     short loc_140BB82B2
0x140bb82a4  mov     edx, 1F7A008Dh
0x140bb82a9  mov     ecx, eax
0x140bb82ab  call    cs:Mso20Win32Client_26547
0x140bb82b1  int     3; Trap to Debugger
0x140bb82b2  test    rsi, rsi
0x140bb82b5  jz      short loc_140BB82C3
0x140bb82b7  xorps   xmm0, xmm0
0x140bb82ba  xor     eax, eax
0x140bb82bc  movups  xmmword ptr [rsi], xmm0
0x140bb82bf  mov     [rsi+10h], rax
0x140bb82c3  mov     word ptr [rsi], 0Dh
0x140bb82c8  mov     [rsi+8], rbx
0x140bb82cc  lea     rcx, [rbp+80h+var_F8]
0x140bb82d0  call    sub_140183210
0x140bb82d5  mov     rcx, [rbp-80h]
0x140bb82e0  test    rcx, rcx
0x140bb82e3  jz      loc_140BB8422
0x140bb82e9  mov     rax, [rcx]
0x140bb82ec  mov     edx, r14d
0x140bb82ef  mov     rax, [rax+0A8h]
0x140bb82f6  call    cs:__guard_dispatch_icall_fptr
0x140bb82fc  nop     dword ptr [rax+00h]
0x140bb8300  jmp     loc_140BB8422
0x140bb8305  lea     rdx, [rsp+180h+var_108]
0x140bb830a  mov     rcx, rdi
0x140bb830d  call    cs:Mso20Win32Client_61346
0x140bb8313  nop
0x140bb8314  lea     rdx, [rsp+180h+var_108]
0x140bb8319  cmp     [rbp+80h+var_F0], 7
0x140bb831e  cmova   rdx, [rsp+180h+var_108]
0x140bb8324  mov     rcx, rsi
0x140bb8327  call    sub_140ACA1E0
0x140bb832c  nop
0x140bb832d  lea     rcx, [rsp+180h+var_108]
0x140bb8332  call    sub_14007FB80
0x140bb8337  jmp     loc_140BB8422
0x140bb833c  mov     rcx, rdi
0x140bb8340  call    cs:Mso20Win32Client_44442
0x140bb8346  mov     bl, al
0x140bb8348  mov     rcx, rsi; pvarg
0x140bb834b  call    cs:VariantClear
0x140bb8351  test    eax, eax
0x140bb8353  jns     short loc_140BB8367
0x140bb8355  mov     edx, 1F7A008Dh
0x140bb835e  mov     ecx, eax
0x140bb8360  call    cs:Mso20Win32Client_26547
0x140bb8366  int     3; Trap to Debugger
0x140bb8367  test    rsi, rsi
0x140bb836a  jz      short loc_140BB8378
0x140bb836c  xorps   xmm0, xmm0
0x140bb836f  xor     eax, eax
0x140bb8371  movups  xmmword ptr [rsi], xmm0
0x140bb8374  mov     [rsi+10h], rax
0x140bb8378  mov     word ptr [rsi], 0Bh
0x140bb837d  xor     bl, r14b
0x140bb8380  movzx   eax, bl
0x140bb8383  sub     ax, r14w
0x140bb8387  mov     [rsi+8], ax
0x140bb838b  jmp     loc_140BB8422
0x140bb8390  mov     rcx, rdi
0x140bb8393  call    sub_140D69720
0x140bb8398  mov     rcx, rdi
0x140bb839b  test    al, al
0x140bb839d  jz      short loc_140BB83E2
0x140bb839f  nop
0x140bb83a0  call    cs:Mso20Win32Client_52971
0x140bb83a6  mov     ebx, eax
0x140bb83a8  mov     rcx, rsi; pvarg
0x140bb83ab  call    cs:VariantClear
0x140bb83b1  test    eax, eax
0x140bb83b3  jns     short loc_140BB83C7
0x140bb83b5  mov     edx, 1F7A008Dh
0x140bb83be  mov     ecx, eax
0x140bb83c0  call    cs:Mso20Win32Client_26547
0x140bb83c6  int     3; Trap to Debugger
0x140bb83c7  test    rsi, rsi
0x140bb83ca  jz      short loc_140BB83D8
0x140bb83cc  xorps   xmm0, xmm0
0x140bb83cf  xor     eax, eax
0x140bb83d1  movups  xmmword ptr [rsi], xmm0
0x140bb83d4  mov     [rsi+10h], rax
0x140bb83d8  mov     word ptr [rsi], 3
0x140bb83dd  mov     [rsi+8], ebx
0x140bb83e0  jmp     short loc_140BB8422
0x140bb83e2  call    cs:Mso20Win32Client_12657
0x140bb83e8  movaps  xmm6, xmm0
0x140bb83eb  mov     rcx, rsi; pvarg
0x140bb83ee  call    cs:VariantClear
0x140bb83f4  test    eax, eax
0x140bb83f6  jns     short loc_140BB8407
0x140bb83f8  mov     edx, 1F7A008Dh
0x140bb83fe  mov     ecx, eax
0x140bb8400  call    cs:Mso20Win32Client_26547
0x140bb8406  int     3; Trap to Debugger
0x140bb8407  test    rsi, rsi
0x140bb840a  jz      short loc_140BB8418
0x140bb840c  xorps   xmm0, xmm0
0x140bb840f  xor     eax, eax
0x140bb8411  movups  xmmword ptr [rsi], xmm0
0x140bb8414  mov     [rsi+10h], rax
0x140bb8418  mov     word ptr [rsi], 5
0x140bb841d  movsd   qword ptr [rsi+8], xmm6
0x140bb8422  mov     rax, rsi
0x140bb8425  mov     rcx, [rbp+80h+var_40]
0x140bb8429  xor     rcx, rsp
0x140bb842c  call    sub_1408D2BB0
0x140bb8431  lea     r11, [rsp+180h+var_20]
0x140bb8439  mov     rbx, [r11+40h]
0x140bb843d  movaps  xmm6, xmmword ptr [r11-10h]
0x140bb8442  mov     rsp, r11
0x140bb8445  pop     r15
0x140bb8447  pop     r14
0x140bb8449  pop     rdi
0x140bb844a  pop     rsi
0x140bb844b  pop     rbp
0x140bb844c  retn
0x140bb844d  lea     r9, aRichapiexcepti_0; "RichApiException false"
0x140bb8454  mov     edx, 4E3h
0x140bb8459  mov     ecx, 22C7443h
0x140bb845e  mov     r8d, 0Fh
0x140bb8464  call    cs:Mso20Win32Client_58193
0x140bb846a  mov     edx, 8007000Eh
0x140bb846f  lea     rcx, [rbp+80h+pExceptionObject]
0x140bb8473  call    sub_14122BFDC
  ... truncated ...
```
