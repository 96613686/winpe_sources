# CInkStrokeDisp::GetPacketData(long,long,tagVARIANT *)

- ea: `0x1800281c0`
- end: `0x18002850f`
- name: `?GetPacketData@CInkStrokeDisp@@UEAAJJJPEAUtagVARIANT@@@Z`
- size: `847`
- prototype: `int(CInkStrokeDisp *__hidden this, int, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002740`
- `0x180010350`
- `0x1800281c0`
- `0x18002e6ec`
- `0x18003312c`
- `0x180044ac6`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800284d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800284e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800284f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800284d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800284e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800284f4`
- `OLEAUT32!__imp_VariantInit` at `0x180028258`
- `OLEAUT32!__imp_VariantInit` at `0x180028258`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800284b2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800284b2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800283b3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800283b3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002848c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002848c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180028399`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180028399`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180028227`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180028227`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkStrokeDisp::GetPacketData(CInkStrokeDisp *this, int a2, int a3, struct tagVARIANT *a4)
{
  HANDLE *v8; // r15
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  HRESULT InkPacketSize; // ebx
  BOOL v13; // r12d
  unsigned __int64 v14; // r13
  unsigned __int64 v15; // r8
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v17; // r14
  char *v18; // r12
  int v19; // r13d
  unsigned int i; // esi
  HRESULT v21; // eax
  struct tagVARIANT *v22; // rax
  DWORD Size; // [rsp+30h] [rbp-58h] BYREF
  unsigned int Size_4; // [rsp+34h] [rbp-54h] BYREF
  BOOL v26; // [rsp+38h] [rbp-50h]
  void *ppvData; // [rsp+40h] [rbp-48h] BYREF
  HANDLE *v28; // [rsp+48h] [rbp-40h]
  DWORD dwindex; // [rsp+90h] [rbp+8h] BYREF
  HRESULT v30; // [rsp+98h] [rbp+10h]
  struct tagVARIANT *v31; // [rsp+A8h] [rbp+20h]

  v31 = a4;
  v30 = a2;
  ppvData = (void *)(((unsigned __int64)this + 24) & -(__int64)(this != (CInkStrokeDisp *)8));
  dwindex = 0;
  v8 = (HANDLE *)((char *)ppvData + 8);
  v28 = (HANDLE *)((char *)ppvData + 8);
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)ppvData + 1, &dwindex);
  if ( a2 < 0 || a3 < -1 || !a3 )
  {
    ReleaseMutex(*v8);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    ReleaseMutex(*v8);
    return 2147500035LL;
  }
  VariantInit(a4);
  try
  {
    v9 = *((_QWORD *)this + 6);
    if ( !v9 )
      goto LABEL_42;
    v10 = *(_QWORD *)(v9 + 24);
    if ( !v10 )
      goto LABEL_42;
    if ( !*(_QWORD *)(v10 + 112) )
      goto LABEL_42;
    v11 = *(_QWORD *)(v9 + 16);
    if ( !v11 || !*(_QWORD *)(v11 + 16) )
      goto LABEL_42;
    Size_4 = 0;
    InkPacketSize = (*(__int64 (__fastcall **)(CInkStrokeDisp *, unsigned int *))(*(_QWORD *)this + 128LL))(
                      this,
                      &Size_4);
    if ( InkPacketSize >= 0 )
    {
      if ( a2 >= Size_4 )
      {
        InkPacketSize = -2147024809;
        goto LABEL_48;
      }
      if ( a3 == -1 || a2 + a3 > Size_4 )
        a3 = Size_4 - a2;
      dwindex = 0;
      Size = 0;
      InkPacketSize = InkStroke_GetInkPacketSize(
                        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 16LL) + 16LL),
                        &dwindex);
      if ( InkPacketSize < 0 )
        goto LABEL_48;
      InkPacketSize = (*(__int64 (__fastcall **)(CInkStrokeDisp *, DWORD *))(*(_QWORD *)this + 136LL))(this, &Size);
      if ( InkPacketSize < 0 )
        goto LABEL_48;
      v13 = dwindex > Size;
      v26 = v13;
      ppvData = 0;
      v14 = a3 * (dwindex >> 2);
      if ( v14 >= a3 * ((unsigned __int64)dwindex >> 2) )
      {
        v15 = a3 * (Size >> 2);
        if ( v15 >= a3 * ((unsigned __int64)Size >> 2) )
        {
          Vector = SafeArrayCreateVector(3u, 0, v15);
          v17 = Vector;
          if ( !Vector )
          {
            InkPacketSize = -2147024882;
            goto LABEL_48;
          }
          InkPacketSize = SafeArrayAccessData(Vector, &ppvData);
          if ( InkPacketSize < 0 )
            goto LABEL_40;
          if ( v13 )
          {
            v18 = (char *)WinMalloc(saturated_mul(v14, 4u));
            if ( !v18 )
              InkPacketSize = -2147024882;
            v19 = 0;
            if ( InkPacketSize < 0 )
            {
LABEL_32:
              for ( i = 0; i < a3; ++i )
              {
                if ( InkPacketSize < 0 )
                  break;
                memcpy_0((char *)ppvData + Size * i, &v18[dwindex * i], Size);
              }
              if ( v18 )
                WinFree(v18);
LABEL_37:
              v21 = SafeArrayUnaccessData(v17);
              if ( InkPacketSize >= 0 )
              {
                InkPacketSize = v21;
                if ( v21 >= 0 )
                {
                  v22 = v31;
                  v31->vt = 8195;
                  v22->llVal = (LONGLONG)v17;
                  goto LABEL_48;
                }
              }
LABEL_40:
              SafeArrayDestroy(v17);
              goto LABEL_48;
            }
          }
          else
          {
            v18 = (char *)ppvData;
            v19 = 0;
          }
          do
          {
            if ( v19 >= a3 )
              break;
            InkPacketSize = InkStroke_GetInkPacket(
                              *(CInkStroke **)(*(_QWORD *)(*((_QWORD *)this + 6) + 16LL) + 16LL),
                              v19 + v30);
            ++v19;
          }
          while ( InkPacketSize >= 0 );
          if ( !v26 )
            goto LABEL_37;
          goto LABEL_32;
        }
      }
LABEL_42:
      InkPacketSize = -2147418113;
    }
  }
  catch ( ... )
  {
    v30 = ReportWispException();
    InkPacketSize = v30;
    v8 = v28;
  }
LABEL_48:
  ReleaseMutex(*v8);
  return (unsigned int)InkPacketSize;
}

```

## disassembly

```asm
0x1800281c0  mov     [rsp+arg_18], r9
0x1800281c5  mov     [rsp+arg_8], edx
0x1800281c9  push    rbx
0x1800281ca  push    rsi
0x1800281cb  push    rdi
0x1800281cc  push    r12
0x1800281ce  push    r13
0x1800281d0  push    r14
0x1800281d2  push    r15
0x1800281d4  sub     rsp, 50h
0x1800281d8  mov     rbx, r9
0x1800281db  mov     edi, r8d
0x1800281de  mov     r14d, edx
0x1800281e1  mov     rsi, rcx
0x1800281e4  lea     rax, [rcx-8]
0x1800281e8  lea     r10, [rcx+18h]
0x1800281ec  neg     rax
0x1800281ef  sbb     r11, r11
0x1800281f2  and     r11, r10
0x1800281f5  mov     [rsp+88h+ppvData], r11
0x1800281fa  xor     r13d, r13d
0x1800281fd  mov     [rsp+88h+dwindex], r13d
0x180028205  lea     r15, [r11+8]
0x180028209  mov     [rsp+88h+var_40], r15
0x18002820e  lea     rax, [rsp+88h+dwindex]
0x180028216  mov     [rsp+88h+lpdwindex], rax; lpdwindex
0x18002821b  mov     r9, r15; pHandles
0x18002821e  lea     r8d, [r13+1]; cHandles
0x180028222  or      edx, 0FFFFFFFFh; dwTimeout
0x180028225  xor     ecx, ecx; dwFlags
0x180028227  call    cs:__imp_CoWaitForMultipleHandles
0x18002822d  nop
0x18002822e  test    r14d, r14d
0x180028231  js      loc_1800284F1
0x180028237  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002823b  cmp     edi, r12d
0x18002823e  jl      loc_1800284F1
0x180028244  test    edi, edi
0x180028246  jz      loc_1800284F1
0x18002824c  test    rbx, rbx
0x18002824f  jz      loc_1800284E1
0x180028255  mov     rcx, rbx; pvarg
0x180028258  call    cs:__imp_VariantInit
0x18002825e  mov     rax, [rsi+30h]
0x180028262  test    rax, rax
0x180028265  jz      loc_1800284C1
0x18002826b  mov     rcx, [rax+18h]
0x18002826f  test    rcx, rcx
0x180028272  jz      loc_1800284C1
0x180028278  cmp     [rcx+70h], r13
0x18002827c  jz      loc_1800284C1
0x180028282  mov     rcx, [rax+10h]
0x180028286  test    rcx, rcx
0x180028289  jz      loc_1800284C1
0x18002828f  cmp     [rcx+10h], r13
0x180028293  jz      loc_1800284C1
0x180028299  mov     dword ptr [rsp+88h+Size+4], r13d
0x18002829e  mov     rax, [rsi]
0x1800282a1  lea     rdx, [rsp+88h+Size+4]
0x1800282a6  mov     rcx, rsi
0x1800282a9  mov     rax, [rax+80h]
0x1800282b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282b5  mov     ebx, eax
0x1800282b7  test    eax, eax
0x1800282b9  js      loc_1800284C6
0x1800282bf  mov     ecx, dword ptr [rsp+88h+Size+4]
0x1800282c3  cmp     r14d, ecx
0x1800282c6  jb      short loc_1800282D2
0x1800282c8  mov     ebx, 80070057h
0x1800282cd  jmp     loc_1800284C6
0x1800282d2  cmp     edi, r12d
0x1800282d5  jz      short loc_1800282DF
0x1800282d7  lea     eax, [r14+rdi]
0x1800282db  cmp     eax, ecx
0x1800282dd  jbe     short loc_1800282E4
0x1800282df  mov     edi, ecx
0x1800282e1  sub     edi, r14d
0x1800282e4  mov     [rsp+88h+dwindex], r13d
0x1800282ec  mov     dword ptr [rsp+88h+Size], r13d
0x1800282f1  mov     rax, [rsi+30h]
0x1800282f5  mov     rcx, [rax+10h]
0x1800282f9  lea     rdx, [rsp+88h+dwindex]
0x180028301  mov     rcx, [rcx+10h]
0x180028305  call    InkStroke_GetInkPacketSize
0x18002830a  mov     ebx, eax
0x18002830c  test    eax, eax
0x18002830e  js      loc_1800284C6
0x180028314  mov     rax, [rsi]
0x180028317  lea     rdx, [rsp+88h+Size]
0x18002831c  mov     rcx, rsi
0x18002831f  mov     rax, [rax+88h]
0x180028326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002832b  mov     ebx, eax
0x18002832d  test    eax, eax
0x18002832f  js      loc_1800284C6
0x180028335  mov     r12d, r13d
0x180028338  mov     ecx, [rsp+88h+dwindex]
0x18002833f  mov     edx, dword ptr [rsp+88h+Size]
0x180028343  cmp     ecx, edx
0x180028345  setnbe  r12b
0x180028349  mov     [rsp+88h+var_50], r12d
0x18002834e  mov     [rsp+88h+ppvData], r13
0x180028353  movsxd  r9, edi
0x180028356  mov     r13d, ecx
0x180028359  shr     r13d, 2
0x18002835d  imul    r13d, edi
0x180028361  mov     eax, ecx
0x180028363  shr     rax, 2
0x180028367  imul    rax, r9
0x18002836b  cmp     r13, rax
0x18002836e  jb      loc_1800284C1
0x180028374  mov     r8d, edx
0x180028377  shr     r8d, 2
0x18002837b  imul    r8d, edi; cElements
0x18002837f  mov     eax, edx
0x180028381  shr     rax, 2
0x180028385  imul    rax, r9
0x180028389  cmp     r8, rax
0x18002838c  jb      loc_1800284C1
0x180028392  mov     ecx, 3; vt
0x180028397  xor     edx, edx; lLbound
0x180028399  call    cs:__imp_SafeArrayCreateVector
0x18002839f  mov     r14, rax
0x1800283a2  test    rax, rax
0x1800283a5  jz      loc_1800284BA
0x1800283ab  lea     rdx, [rsp+88h+ppvData]; ppvData
0x1800283b0  mov     rcx, rax; psa
0x1800283b3  call    cs:__imp_SafeArrayAccessData
0x1800283b9  mov     ebx, eax
0x1800283bb  test    eax, eax
0x1800283bd  js      loc_1800284AF
0x1800283c3  test    r12d, r12d
0x1800283c6  jz      short loc_1800283FA
0x1800283c8  mov     eax, 4
0x1800283cd  mul     r13
0x1800283d0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800283d7  cmovb   rax, rcx
0x1800283db  mov     rcx, rax; unsigned __int64
0x1800283de  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800283e3  mov     r12, rax
0x1800283e6  mov     eax, 8007000Eh
0x1800283eb  test    r12, r12
0x1800283ee  cmovz   ebx, eax
0x1800283f1  xor     r13d, r13d
0x1800283f4  test    ebx, ebx
0x1800283f6  jns     short loc_180028402
0x1800283f8  jmp     short loc_180028449
0x1800283fa  mov     r12, [rsp+88h+ppvData]
0x1800283ff  xor     r13d, r13d
0x180028402  cmp     r13d, edi
0x180028405  jge     short loc_180028442
0x180028407  mov     r9d, r13d
0x18002840a  imul    r9d, [rsp+88h+dwindex]
0x180028413  add     r9, r12
0x180028416  mov     edx, [rsp+88h+arg_8]
0x18002841d  add     edx, r13d; int
0x180028420  mov     rax, [rsi+30h]
0x180028424  mov     rcx, [rax+10h]
0x180028428  mov     r8d, [rsp+88h+dwindex]
0x180028430  mov     rcx, [rcx+10h]; this
0x180028434  call    InkStroke_GetInkPacket
0x180028439  mov     ebx, eax
0x18002843b  inc     r13d
0x18002843e  test    eax, eax
0x180028440  jns     short loc_180028402
0x180028442  cmp     [rsp+88h+var_50], 0
0x180028447  jz      short loc_180028489
0x180028449  xor     esi, esi
0x18002844b  test    edi, edi
0x18002844d  jz      short loc_18002847C
0x18002844f  test    ebx, ebx
0x180028451  js      short loc_18002847C
0x180028453  mov     r8d, dword ptr [rsp+88h+Size]; Size
0x180028458  mov     edx, esi
0x18002845a  imul    edx, [rsp+88h+dwindex]
0x180028462  add     rdx, r12; Src
0x180028465  mov     ecx, esi
0x180028467  imul    ecx, dword ptr [rsp+88h+Size]
0x18002846c  add     rcx, [rsp+88h+ppvData]; void *
0x180028471  call    memcpy_0
0x180028476  inc     esi
0x180028478  cmp     esi, edi
0x18002847a  jb      short loc_18002844F
0x18002847c  test    r12, r12
0x18002847f  jz      short loc_180028489
0x180028481  mov     rcx, r12; void *
0x180028484  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x180028489  mov     rcx, r14; psa
0x18002848c  call    cs:__imp_SafeArrayUnaccessData
0x180028492  test    ebx, ebx
0x180028494  js      short loc_1800284AF
0x180028496  mov     ebx, eax
0x180028498  test    eax, eax
0x18002849a  js      short loc_1800284AF
0x18002849c  mov     rax, [rsp+88h+arg_18]
0x1800284a4  mov     word ptr [rax], 2003h
0x1800284a9  mov     [rax+8], r14
0x1800284ad  jmp     short loc_1800284C6
0x1800284af  mov     rcx, r14; psa
0x1800284b2  call    cs:__imp_SafeArrayDestroy
0x1800284b8  jmp     short loc_1800284C6
0x1800284ba  mov     ebx, 8007000Eh
0x1800284bf  jmp     short loc_1800284C6
0x1800284c1  mov     ebx, 8000FFFFh
0x1800284c6  jmp     short loc_1800284D4
0x1800284c8  mov     ebx, [rsp+88h+arg_8]
0x1800284cf  mov     r15, [rsp+88h+var_40]
0x1800284d4  mov     rcx, [r15]; hMutex
0x1800284d7  call    cs:__imp_ReleaseMutex
0x1800284dd  mov     eax, ebx
0x1800284df  jmp     short loc_1800284FF
0x1800284e1  mov     rcx, [r15]; hMutex
0x1800284e4  call    cs:__imp_ReleaseMutex
0x1800284ea  mov     eax, 80004003h
0x1800284ef  jmp     short loc_1800284FF
0x1800284f1  mov     rcx, [r15]; hMutex
0x1800284f4  call    cs:__imp_ReleaseMutex
0x1800284fa  mov     eax, 80070057h
0x1800284ff  add     rsp, 50h
0x180028503  pop     r15
0x180028505  pop     r14
0x180028507  pop     r13
0x180028509  pop     r12
0x18002850b  pop     rdi
0x18002850c  pop     rsi
0x18002850d  pop     rbx
0x18002850e  retn
```
