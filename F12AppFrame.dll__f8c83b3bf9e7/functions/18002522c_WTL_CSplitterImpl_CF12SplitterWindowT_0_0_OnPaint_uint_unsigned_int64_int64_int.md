# WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x18002522c`
- end: `0x180025439`
- name: `?OnPaint@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAA_JI_K_JAEAH@Z`
- size: `525`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180027544`

## callees

- `0x180001800`
- `0x1800226b4`
- `0x18002522c`
- `0x1800288a0`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x1800253b1`
- `GDI32!CreateSolidBrush` at `0x1800253b1`
- `GDI32!DeleteObject` at `0x1800253cd`
- `GDI32!DeleteObject` at `0x1800253cd`
- `USER32!FillRect` at `0x1800253a4`
- `USER32!FillRect` at `0x1800253c4`
- `USER32!FillRect` at `0x1800253a4`
- `USER32!FillRect` at `0x1800253c4`
- `USER32!EndPaint` at `0x18002540d`
- `USER32!EndPaint` at `0x18002540d`
- `USER32!BeginPaint` at `0x18002529e`
- `USER32!BeginPaint` at `0x18002529e`
- `USER32!SystemParametersInfoW` at `0x180025387`
- `USER32!SystemParametersInfoW` at `0x180025387`

## pseudocode

```c
__int64 __fastcall WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::OnPaint(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  HDC v5; // rax
  __int64 v6; // rdi
  HDC v7; // rsi
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rax
  int v11; // r8d
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // edx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // ecx
  HBRUSH SolidBrush; // rbx
  __int64 v20; // rbx
  __int128 pvParam; // [rsp+20h] [rbp-51h] BYREF
  HDC v23; // [rsp+30h] [rbp-41h]
  HWND hWnd; // [rsp+38h] [rbp-39h]
  struct tagPAINTSTRUCT Paint; // [rsp+40h] [rbp-31h] BYREF
  RECT rc; // [rsp+90h] [rbp+1Fh] BYREF

  v3 = a1;
  if ( *(_DWORD *)(a1 + 72) == -1 && *(_DWORD *)(a1 + 32) == -1 )
  {
    LOBYTE(a3) = 1;
    if ( !a1 )
      a1 = 72;
    WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::SetSplitterPos(a1, 0xFFFFFFFFLL, a3);
  }
  v23 = 0;
  v4 = v3 - 64;
  if ( !v3 )
    v4 = 8;
  hWnd = *(HWND *)v4;
  v5 = BeginPaint(hWnd, &Paint);
  v6 = v3;
  v7 = v5;
  v23 = v5;
  if ( !v3 )
    v6 = 72;
  v8 = *(int *)(v6 + 72);
  if ( (_DWORD)v8 == -1 )
  {
    if ( *(_DWORD *)(v6 + 32) != -1 )
    {
      v9 = v3 + 72;
      if ( !v3 )
        v9 = 144;
      if ( *(_DWORD *)v9 == -1 )
      {
        v10 = v3 + 32;
        if ( !v3 )
          v10 = 104;
        v11 = *(_DWORD *)v10;
        if ( *(_DWORD *)v10 != -1 )
        {
          v12 = v3 + 16;
          if ( !v3 )
            v12 = 88;
          pvParam = 0;
          rc.left = *(_DWORD *)v12;
          v13 = v3 + 20;
          if ( !v3 )
            v13 = 92;
          v14 = *(_DWORD *)v13;
          rc.top = *(_DWORD *)v13 + v11;
          v15 = v3 + 24;
          if ( !v3 )
            v15 = 96;
          v16 = v3 + 48;
          rc.right = *(_DWORD *)v15;
          if ( !v3 )
            v16 = 120;
          v17 = v3 + 40;
          if ( !v3 )
            v17 = 112;
          v18 = v14 + *(_DWORD *)v17 + *(_DWORD *)v16;
          LODWORD(pvParam) = 16;
          rc.bottom = v11 + v18;
          if ( SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) && (BYTE4(pvParam) & 1) != 0 )
          {
            FillRect(v7, &rc, (HBRUSH)7);
          }
          else
          {
            SolidBrush = CreateSolidBrush(0xDBCECCu);
            FillRect(v7, &rc, SolidBrush);
            DeleteObject(SolidBrush);
          }
        }
      }
      v20 = 0;
      do
      {
        if ( !*(_QWORD *)(v6 + 8 * v20) )
          WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::DrawSplitterPane(v6, v7);
        v20 = (unsigned int)(v20 + 1);
      }
      while ( (int)v20 < 2 );
    }
  }
  else if ( !*(_QWORD *)(v6 + 8 * v8) )
  {
    WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::DrawSplitterPane(v6, v5);
  }
  EndPaint(hWnd, &Paint);
  return 0;
}

```

## disassembly

```asm
0x18002522c  mov     [rsp-8+arg_8], rbx
0x180025231  mov     [rsp-8+arg_10], rsi
0x180025236  push    rbp
0x180025237  push    rdi
0x180025238  push    r12
0x18002523a  lea     rbp, [rsp-3Fh]
0x18002523f  sub     rsp, 0B0h
0x180025246  mov     rax, cs:__security_cookie
0x18002524d  xor     rax, rsp
0x180025250  mov     [rbp+4Fh+var_20], rax
0x180025254  cmp     dword ptr [rcx+48h], 0FFFFFFFFh
0x180025258  mov     rbx, rcx
0x18002525b  mov     r12d, 48h ; 'H'
0x180025261  jnz     short loc_18002527B
0x180025263  cmp     dword ptr [rcx+20h], 0FFFFFFFFh
0x180025267  jnz     short loc_18002527B
0x180025269  test    rcx, rcx
0x18002526c  mov     r8b, 1
0x18002526f  cmovz   rcx, r12
0x180025273  or      edx, 0FFFFFFFFh
0x180025276  call    ?SetSplitterPos@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAA_NH_N@Z; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::SetSplitterPos(int,bool)
0x18002527b  mov     ecx, 8
0x180025280  mov     [rbp+4Fh+var_90], 0
0x180025288  test    rbx, rbx
0x18002528b  lea     rax, [rbx-40h]
0x18002528f  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x180025293  cmovz   rax, rcx
0x180025297  mov     rcx, [rax]; hWnd
0x18002529a  mov     [rbp+4Fh+hWnd], rcx
0x18002529e  call    cs:__imp_BeginPaint
0x1800252a4  test    rbx, rbx
0x1800252a7  mov     rdi, rbx
0x1800252aa  mov     rsi, rax
0x1800252ad  mov     [rbp+4Fh+var_90], rax
0x1800252b1  cmovz   rdi, r12
0x1800252b5  movsxd  r8, dword ptr [rdi+48h]
0x1800252b9  cmp     r8d, 0FFFFFFFFh
0x1800252bd  jnz     loc_1800253F3
0x1800252c3  cmp     [rdi+20h], r8d
0x1800252c7  jz      loc_180025405
0x1800252cd  cmp     r8d, r8d
0x1800252d0  jnz     loc_1800253F3
0x1800252d6  test    rbx, rbx
0x1800252d9  lea     rax, [rbx+48h]
0x1800252dd  mov     ecx, 90h
0x1800252e2  cmovz   rax, rcx
0x1800252e6  cmp     [rax], r8d
0x1800252e9  jnz     loc_1800253D3
0x1800252ef  test    rbx, rbx
0x1800252f2  lea     ecx, [r8+69h]
0x1800252f6  lea     rax, [rbx+20h]
0x1800252fa  cmovz   rax, rcx
0x1800252fe  mov     r8d, [rax]
0x180025301  cmp     r8d, 0FFFFFFFFh
0x180025305  jz      loc_1800253D3
0x18002530b  test    rbx, rbx
0x18002530e  lea     rax, [rbx+10h]
0x180025312  mov     r9d, 70h ; 'p'
0x180025318  mov     ecx, 58h ; 'X'
0x18002531d  cmovz   rax, rcx
0x180025321  xorps   xmm0, xmm0
0x180025324  mov     ecx, 5Ch ; '\'
0x180025329  movups  [rbp+4Fh+pvParam], xmm0
0x18002532d  mov     eax, [rax]
0x18002532f  mov     [rbp+4Fh+rc.left], eax
0x180025332  lea     rax, [rbx+14h]
0x180025336  cmovz   rax, rcx
0x18002533a  mov     ecx, 60h ; '`'
0x18002533f  mov     edx, [rax]
0x180025341  lea     eax, [rdx+r8]
0x180025345  mov     [rbp+4Fh+rc.top], eax
0x180025348  lea     rax, [rbx+18h]
0x18002534c  cmovz   rax, rcx
0x180025350  lea     rcx, [rbx+30h]
0x180025354  mov     eax, [rax]
0x180025356  mov     [rbp+4Fh+rc.right], eax
0x180025359  mov     eax, 78h ; 'x'
0x18002535e  cmovz   rcx, rax
0x180025362  lea     rax, [rbx+28h]
0x180025366  cmovz   rax, r9
0x18002536a  mov     ecx, [rcx]
0x18002536c  add     ecx, [rax]
0x18002536e  add     ecx, edx
0x180025370  lea     edx, [r9-60h]; uiParam
0x180025374  add     ecx, r8d
0x180025377  mov     dword ptr [rbp+4Fh+pvParam], edx
0x18002537a  mov     [rbp+4Fh+rc.bottom], ecx
0x18002537d  lea     r8, [rbp+4Fh+pvParam]; pvParam
0x180025381  lea     ecx, [rdx+32h]; uiAction
0x180025384  xor     r9d, r9d; fWinIni
0x180025387  call    cs:__imp_SystemParametersInfoW
0x18002538d  test    eax, eax
0x18002538f  jz      short loc_1800253AC
0x180025391  test    byte ptr [rbp+4Fh+pvParam+4], 1
0x180025395  jz      short loc_1800253AC
0x180025397  mov     r8d, 7; hbr
0x18002539d  lea     rdx, [rbp+4Fh+rc]; lprc
0x1800253a1  mov     rcx, rsi; hDC
0x1800253a4  call    cs:__imp_FillRect
0x1800253aa  jmp     short loc_1800253D3
0x1800253ac  mov     ecx, 0DBCECCh; color
0x1800253b1  call    cs:__imp_CreateSolidBrush
0x1800253b7  lea     rdx, [rbp+4Fh+rc]; lprc
0x1800253bb  mov     rcx, rsi; hDC
0x1800253be  mov     r8, rax; hbr
0x1800253c1  mov     rbx, rax
0x1800253c4  call    cs:__imp_FillRect
0x1800253ca  mov     rcx, rbx; ho
0x1800253cd  call    cs:__imp_DeleteObject
0x1800253d3  xor     ebx, ebx
0x1800253d5  cmp     qword ptr [rdi+rbx*8], 0
0x1800253da  jnz     short loc_1800253EA
0x1800253dc  mov     r8d, ebx
0x1800253df  mov     rdx, rsi
0x1800253e2  mov     rcx, rdi
0x1800253e5  call    ?DrawSplitterPane@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAAXV?$CDCT@$0A@@2@H@Z; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::DrawSplitterPane(WTL::CDCT<0>,int)
0x1800253ea  inc     ebx
0x1800253ec  cmp     ebx, 2
0x1800253ef  jl      short loc_1800253D5
0x1800253f1  jmp     short loc_180025405
0x1800253f3  cmp     qword ptr [rdi+r8*8], 0
0x1800253f8  jnz     short loc_180025405
0x1800253fa  mov     rdx, rsi
0x1800253fd  mov     rcx, rdi
0x180025400  call    ?DrawSplitterPane@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAAXV?$CDCT@$0A@@2@H@Z; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::DrawSplitterPane(WTL::CDCT<0>,int)
0x180025405  mov     rcx, [rbp+4Fh+hWnd]; hWnd
0x180025409  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x18002540d  call    cs:__imp_EndPaint
0x180025413  xor     eax, eax
0x180025415  mov     rcx, [rbp+4Fh+var_20]
0x180025419  xor     rcx, rsp; StackCookie
0x18002541c  call    __security_check_cookie
0x180025421  lea     r11, [rsp+0C0h+var_10]
0x180025429  mov     rbx, [r11+28h]
0x18002542d  mov     rsi, [r11+30h]
0x180025431  mov     rsp, r11
0x180025434  pop     r12
0x180025436  pop     rdi
0x180025437  pop     rbp
0x180025438  retn
```
