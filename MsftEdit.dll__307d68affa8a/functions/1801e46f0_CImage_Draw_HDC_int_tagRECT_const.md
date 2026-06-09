# CImage::Draw(HDC__ *,int,tagRECT const *)

- ea: `0x1801e46f0`
- end: `0x1801e48fc`
- name: `?Draw@CImage@@UEAAJPEAUHDC__@@HPEBUtagRECT@@@Z`
- size: `524`
- prototype: `int(CImage *__hidden this, HDC, int, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18006e770`
- `0x1801e46f0`
- `0x1801e6130`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801e48e0`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801e48e0`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801e4737`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801e4737`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x1801e4799`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x1801e4799`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801e4753`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801e48d7`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801e4753`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801e48d7`
- `ext-ms-win-gdi-draw-l1-1-1!GdiAlphaBlend` at `0x1801e4883`
- `ext-ms-win-gdi-draw-l1-1-1!GdiAlphaBlend` at `0x1801e4883`
- `ext-ms-win-gdi-draw-l1-1-0!BitBlt` at `0x1801e48c4`
- `ext-ms-win-gdi-draw-l1-1-0!BitBlt` at `0x1801e48c4`

## pseudocode

```c
__int64 __fastcall CImage::Draw(CImage *this, HDC a2, int a3, const struct tagRECT *a4)
{
  unsigned int v8; // edi
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rsi
  HGDIOBJ v11; // r15
  void *v12; // rcx
  LONG left; // eax
  LONG top; // r13d
  int v15; // eax
  int v16; // eax
  int yoriginSrc; // eax
  float v18; // xmm1_4
  BLENDFUNCTION ftn; // [rsp+60h] [rbp-78h]
  int x1; // [rsp+64h] [rbp-74h]
  int xoriginDest; // [rsp+68h] [rbp-70h]
  _OWORD pv[6]; // [rsp+70h] [rbp-68h] BYREF

  v8 = CImage::CheckGdiBitmap(this, a2, a4);
  if ( !v8 )
  {
    if ( *((_QWORD *)this + 16) )
    {
      v8 = -2147467259;
      CompatibleDC = CreateCompatibleDC(0);
      hdcSrc = CompatibleDC;
      if ( CompatibleDC )
      {
        v11 = SelectObject(CompatibleDC, *((HGDIOBJ *)this + 16));
        if ( v11 )
        {
          v12 = (void *)*((_QWORD *)this + 16);
          memset(pv, 0, 32);
          if ( GetObjectW(v12, 32, pv) == 32 )
          {
            left = a4->left;
            top = a4->top;
            xoriginDest = left;
            v15 = (*(__int64 (__fastcall **)(CImage *))(*(_QWORD *)this + 104LL))(this);
            x1 = CW32System::MulDivFunc(*((_DWORD *)this + 44), v15, 2540);
            v16 = (*(__int64 (__fastcall **)(CImage *))(*(_QWORD *)this + 112LL))(this);
            yoriginSrc = CW32System::MulDivFunc(*((_DWORD *)this + 45), v16, 2540);
            v18 = *((float *)this + 51);
            if ( (v18 >= 1.0 || a3) && !*((_BYTE *)this + 211) )
            {
              if ( BitBlt(
                     a2,
                     xoriginDest,
                     top,
                     *((_DWORD *)this + 48),
                     *((_DWORD *)this + 49),
                     hdcSrc,
                     x1,
                     yoriginSrc,
                     a3 != 0 ? 3342344 : 13369376) )
              {
                v8 = 0;
              }
            }
            else
            {
              ftn.AlphaFormat = *((_BYTE *)this + 211) != 0;
              *(_WORD *)&ftn.BlendOp = 0;
              ftn.SourceConstantAlpha = (int)(float)(v18 * 255.0);
              v8 = !GdiAlphaBlend(
                      a2,
                      xoriginDest,
                      top,
                      *((_DWORD *)this + 48),
                      *((_DWORD *)this + 49),
                      hdcSrc,
                      x1,
                      yoriginSrc,
                      *((_DWORD *)this + 48),
                      *((_DWORD *)this + 49),
                      ftn)
                 ? 0x80004005
                 : 0;
            }
            SelectObject(hdcSrc, v11);
          }
        }
        DeleteDC(hdcSrc);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1801e46f0  push    rbx
0x1801e46f2  push    rbp
0x1801e46f3  push    rsi
0x1801e46f4  push    rdi
0x1801e46f5  push    r12
0x1801e46f7  push    r13
0x1801e46f9  push    r14
0x1801e46fb  push    r15
0x1801e46fd  sub     rsp, 98h
0x1801e4704  mov     r12d, r8d
0x1801e4707  mov     r13, r9
0x1801e470a  mov     r8, r9; struct tagRECT *
0x1801e470d  mov     r14, rdx
0x1801e4710  mov     rbx, rcx
0x1801e4713  call    ?CheckGdiBitmap@CImage@@AEAAJPEAUHDC__@@PEBUtagRECT@@@Z; CImage::CheckGdiBitmap(HDC__ *,tagRECT const *)
0x1801e4718  mov     edi, eax
0x1801e471a  test    eax, eax
0x1801e471c  jnz     loc_1801E48E6
0x1801e4722  cmp     qword ptr [rbx+80h], 0
0x1801e472a  jz      loc_1801E48E6
0x1801e4730  xor     ecx, ecx; hdc
0x1801e4732  mov     edi, 80004005h
0x1801e4737  call    cs:__imp_CreateCompatibleDC
0x1801e473d  mov     rsi, rax
0x1801e4740  test    rax, rax
0x1801e4743  jz      loc_1801E48E6
0x1801e4749  mov     rdx, [rbx+80h]; h
0x1801e4750  mov     rcx, rax; hdc
0x1801e4753  call    cs:__imp_SelectObject
0x1801e4759  mov     r15, rax
0x1801e475c  test    rax, rax
0x1801e475f  jz      loc_1801E48DD
0x1801e4765  xorps   xmm0, xmm0
0x1801e4768  lea     r8, [rsp+0D8h+pv]; pv
0x1801e476d  mov     ecx, r12d
0x1801e4770  mov     edx, 20h ; ' '; c
0x1801e4775  neg     ecx
0x1801e4777  mov     rcx, [rbx+80h]; h
0x1801e477e  sbb     ebp, ebp
0x1801e4780  and     ebp, 0FF66FFE8h
0x1801e4786  add     ebp, 0CC0020h
0x1801e478c  movups  [rsp+0D8h+pv], xmm0
0x1801e4791  movups  [rsp+0D8h+var_58], xmm0
0x1801e4799  call    cs:__imp_GetObjectW
0x1801e479f  cmp     eax, 20h ; ' '
0x1801e47a2  jnz     loc_1801E48DD
0x1801e47a8  mov     eax, [r13+0]
0x1801e47ac  mov     rcx, rbx
0x1801e47af  mov     r13d, [r13+4]
0x1801e47b3  mov     [rsp+0D8h+xoriginDest], eax
0x1801e47b7  mov     rax, [rbx]
0x1801e47ba  mov     rax, [rax+68h]
0x1801e47be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e47c3  mov     ecx, [rbx+0B0h]; int
0x1801e47c9  mov     r8d, 9ECh; int
0x1801e47cf  mov     edx, eax; int
0x1801e47d1  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x1801e47d6  mov     rcx, [rbx]
0x1801e47d9  mov     [rsp+0D8h+x1], eax
0x1801e47dd  mov     rax, [rcx+70h]
0x1801e47e1  mov     rcx, rbx
0x1801e47e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e47e9  mov     ecx, [rbx+0B4h]; int
0x1801e47ef  mov     r8d, 9ECh; int
0x1801e47f5  mov     edx, eax; int
0x1801e47f7  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x1801e47fc  movss   xmm1, dword ptr [rbx+0CCh]
0x1801e4804  mov     r11d, eax
0x1801e4807  movss   xmm0, cs:__real@3f800000
0x1801e480f  comiss  xmm0, xmm1
0x1801e4812  jbe     short loc_1801E4819
0x1801e4814  test    r12d, r12d
0x1801e4817  jz      short loc_1801E4822
0x1801e4819  cmp     byte ptr [rbx+0D3h], 0
0x1801e4820  jz      short loc_1801E4893
0x1801e4822  mov     ecx, [rbx+0C4h]
0x1801e4828  mov     r8d, r13d; yoriginDest
0x1801e482b  mulss   xmm1, cs:__real@437f0000
0x1801e4833  cmp     byte ptr [rbx+0D3h], 0
0x1801e483a  mov     r9d, [rbx+0C0h]; wDest
0x1801e4841  mov     edx, [rsp+0D8h+xoriginDest]; xoriginDest
0x1801e4845  setnz   [rsp+0D8h+var_78.AlphaFormat]
0x1801e484a  cvttss2si eax, xmm1
0x1801e484e  mov     word ptr [rsp+0D8h+var_78.BlendOp], 0
0x1801e4855  mov     [rsp+0D8h+var_78.SourceConstantAlpha], al
0x1801e4859  mov     eax, dword ptr [rsp+0D8h+var_78.BlendOp]
0x1801e485d  mov     dword ptr [rsp+0D8h+ftn.BlendOp], eax; ftn
0x1801e4861  mov     eax, [rsp+0D8h+x1]
0x1801e4865  mov     [rsp+0D8h+hSrc], ecx; hSrc
0x1801e4869  mov     [rsp+0D8h+wSrc], r9d; wSrc
0x1801e486e  mov     [rsp+0D8h+yoriginSrc], r11d; yoriginSrc
0x1801e4873  mov     [rsp+0D8h+xoriginSrc], eax; xoriginSrc
0x1801e4877  mov     [rsp+0D8h+hdcSrc], rsi; hdcSrc
0x1801e487c  mov     [rsp+0D8h+hDest], ecx; hDest
0x1801e4880  mov     rcx, r14; hdcDest
0x1801e4883  call    cs:__imp_GdiAlphaBlend
0x1801e4889  neg     eax
0x1801e488b  sbb     ecx, ecx
0x1801e488d  not     ecx
0x1801e488f  and     edi, ecx
0x1801e4891  jmp     short loc_1801E48D1
0x1801e4893  mov     eax, [rsp+0D8h+x1]
0x1801e4897  mov     r8d, r13d; y
0x1801e489a  mov     r9d, [rbx+0C0h]; cx
0x1801e48a1  mov     rcx, r14; hdc
0x1801e48a4  mov     edx, [rsp+0D8h+xoriginDest]; x
0x1801e48a8  mov     [rsp+0D8h+wSrc], ebp; rop
0x1801e48ac  mov     [rsp+0D8h+yoriginSrc], r11d; y1
0x1801e48b1  mov     [rsp+0D8h+xoriginSrc], eax; x1
0x1801e48b5  mov     eax, [rbx+0C4h]
0x1801e48bb  mov     [rsp+0D8h+hdcSrc], rsi; hdcSrc
0x1801e48c0  mov     [rsp+0D8h+hDest], eax; cy
0x1801e48c4  call    cs:__imp_BitBlt
0x1801e48ca  xor     ecx, ecx
0x1801e48cc  test    eax, eax
0x1801e48ce  cmovnz  edi, ecx
0x1801e48d1  mov     rdx, r15; h
0x1801e48d4  mov     rcx, rsi; hdc
0x1801e48d7  call    cs:__imp_SelectObject
0x1801e48dd  mov     rcx, rsi; hdc
0x1801e48e0  call    cs:__imp_DeleteDC
0x1801e48e6  mov     eax, edi
0x1801e48e8  add     rsp, 98h
0x1801e48ef  pop     r15
0x1801e48f1  pop     r14
0x1801e48f3  pop     r13
0x1801e48f5  pop     r12
0x1801e48f7  pop     rdi
0x1801e48f8  pop     rsi
0x1801e48f9  pop     rbp
0x1801e48fa  pop     rbx
0x1801e48fb  retn
```
