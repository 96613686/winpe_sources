# CTitleBar::_OnNcHitTest(tagPOINT const &,bool *)

- ea: `0x18002ac20`
- end: `0x18002ae58`
- name: `?_OnNcHitTest@CTitleBar@@AEAA_JAEBUtagPOINT@@PEA_N@Z`
- size: `568`
- prototype: `__int64 __fastcall(CTitleBar *__hidden this, const struct tagPOINT *, bool *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18002a2e0`
- `0x18005b048`
- `0x18005b1c8`

## callees

- `0x18002ac20`
- `0x180043c30`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002ac67`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002acaa`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002acc4`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002acdc`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002acf4`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002ad0c`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002ad98`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002ac67`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002acaa`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002acc4`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002acdc`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002acf4`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002ad0c`
- `api-ms-win-ntuser-rectangle-l1-1-0!PtInRect` at `0x18002ad98`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18002ad54`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18002ad54`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x18002ad32`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x18002ad43`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x18002ad32`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x18002ad43`

## pseudocode

```c
__int64 __fastcall CTitleBar::_OnNcHitTest(CTitleBar *this, const struct tagPOINT *a2, bool *a3)
{
  __int64 v6; // rbp
  bool v7; // si
  HWND *v9; // rsi
  bool v10; // zf
  LONG v11; // eax
  LONG v12; // ecx
  RECT rc; // [rsp+20h] [rbp-58h] BYREF

  v6 = 1;
  v7 = (*((_DWORD *)this + 364) & 0x100) != 0 && *((_DWORD *)this + 138) == 1;
  if ( PtInRect((const RECT *)((char *)this + 852), *a2) || v7 && !a2->y )
  {
    if ( PtInRect((const RECT *)((char *)this + 1300), *a2) )
    {
      v6 = 8;
    }
    else if ( PtInRect((const RECT *)((char *)this + 1364), *a2) )
    {
      v6 = 9;
    }
    else if ( PtInRect((const RECT *)((char *)this + 1316), *a2) )
    {
      v6 = 23;
    }
    else if ( PtInRect((const RECT *)((char *)this + 1332), *a2) )
    {
      v6 = 24;
    }
    else if ( PtInRect((const RECT *)((char *)this + 1348), *a2) )
    {
      v6 = 20;
    }
    v9 = (HWND *)((char *)this + 504);
    if ( (*((_BYTE *)this + 1452) & 2) != 0 && !IsZoomed(*v9) )
    {
      v12 = *((_DWORD *)this + 158);
      if ( a2->y <= v12 )
      {
        if ( a2->x >= *((_DWORD *)this + 215) - v12 - *((_DWORD *)this + 213) )
          v6 = 14;
        else
          v6 = (a2->x <= v12) + 12LL;
      }
    }
    if ( IsZoomed(*v9)
      && !IsRectEmpty((const RECT *)((char *)this + 1348))
      && ((v10 = *((_BYTE *)this + 559) == 0,
           v11 = *((_DWORD *)this + 214),
           rc = *(RECT *)((char *)this + 1348),
           rc.top = v11,
           !v10)
       || *((_BYTE *)this + 560)
        ? (rc.left = *((_DWORD *)this + 213))
        : (rc.right = *((_DWORD *)this + 215)),
          PtInRect(&rc, *a2)) )
    {
      v6 = 20;
      *a3 = 1;
    }
    else
    {
      if ( v6 == 1 )
        v6 = 2;
      *a3 = 1;
    }
  }
  else
  {
    *a3 = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18002ac20  push    rbx
0x18002ac22  push    rbp
0x18002ac23  push    rsi
0x18002ac24  push    rdi
0x18002ac25  push    r14
0x18002ac27  push    r15
0x18002ac29  sub     rsp, 48h
0x18002ac2d  mov     rax, cs:__security_cookie
0x18002ac34  xor     rax, rsp
0x18002ac37  mov     [rsp+78h+var_48], rax
0x18002ac3c  test    dword ptr [rcx+5B0h], 100h
0x18002ac46  mov     r15, r8
0x18002ac49  mov     rdi, rdx
0x18002ac4c  mov     rbx, rcx
0x18002ac4f  mov     ebp, 1
0x18002ac54  jnz     loc_18002ADEC
0x18002ac5a  xor     sil, sil
0x18002ac5d  mov     rdx, [rdx]; pt
0x18002ac60  add     rcx, 354h; lprc
0x18002ac67  call    cs:__imp_PtInRect
0x18002ac6d  test    eax, eax
0x18002ac6f  jnz     short loc_18002AC9B
0x18002ac71  test    sil, sil
0x18002ac74  jnz     loc_18002AE3F
0x18002ac7a  mov     byte ptr [r15], 0
0x18002ac7e  mov     rax, rbp
0x18002ac81  mov     rcx, [rsp+78h+var_48]
0x18002ac86  xor     rcx, rsp; StackCookie
0x18002ac89  call    __security_check_cookie
0x18002ac8e  add     rsp, 48h
0x18002ac92  pop     r15
0x18002ac94  pop     r14
0x18002ac96  pop     rdi
0x18002ac97  pop     rsi
0x18002ac98  pop     rbp
0x18002ac99  pop     rbx
0x18002ac9a  retn
0x18002ac9b  mov     rdx, [rdi]; pt
0x18002ac9e  lea     rcx, [rbx+514h]; lprc
0x18002aca5  mov     [rsp+78h+var_38], r12
0x18002acaa  call    cs:__imp_PtInRect
0x18002acb0  mov     r12d, 14h
0x18002acb6  test    eax, eax
0x18002acb8  jnz     short loc_18002AD1A
0x18002acba  mov     rdx, [rdi]; pt
0x18002acbd  lea     rcx, [rbx+554h]; lprc
0x18002acc4  call    cs:__imp_PtInRect
0x18002acca  test    eax, eax
0x18002accc  jnz     loc_18002ADCC
0x18002acd2  mov     rdx, [rdi]; pt
0x18002acd5  lea     rcx, [rbx+524h]; lprc
0x18002acdc  call    cs:__imp_PtInRect
0x18002ace2  test    eax, eax
0x18002ace4  jnz     loc_18002AE01
0x18002acea  mov     rdx, [rdi]; pt
0x18002aced  lea     rcx, [rbx+534h]; lprc
0x18002acf4  call    cs:__imp_PtInRect
0x18002acfa  test    eax, eax
0x18002acfc  jnz     loc_18002ADD6
0x18002ad02  mov     rdx, [rdi]; pt
0x18002ad05  lea     rcx, [rbx+544h]; lprc
0x18002ad0c  call    cs:__imp_PtInRect
0x18002ad12  test    eax, eax
0x18002ad14  cmovnz  rbp, r12
0x18002ad18  jmp     short loc_18002AD1F
0x18002ad1a  mov     ebp, 8
0x18002ad1f  test    byte ptr [rbx+5ACh], 2
0x18002ad26  lea     rsi, [rbx+1F8h]
0x18002ad2d  jz      short loc_18002AD40
0x18002ad2f  mov     rcx, [rsi]; hWnd
0x18002ad32  call    cs:__imp_IsZoomed
0x18002ad38  test    eax, eax
0x18002ad3a  jz      loc_18002AE0B
0x18002ad40  mov     rcx, [rsi]; hWnd
0x18002ad43  call    cs:__imp_IsZoomed
0x18002ad49  test    eax, eax
0x18002ad4b  jz      short loc_18002ADB3
0x18002ad4d  lea     rcx, [rbx+544h]; lprc
0x18002ad54  call    cs:__imp_IsRectEmpty
0x18002ad5a  test    eax, eax
0x18002ad5c  jnz     short loc_18002ADB3
0x18002ad5e  cmp     byte ptr [rbx+22Fh], 0
0x18002ad65  movups  xmm0, xmmword ptr [rbx+544h]
0x18002ad6c  mov     eax, [rbx+358h]
0x18002ad72  movups  xmmword ptr [rsp+78h+rc.left], xmm0
0x18002ad77  mov     [rsp+78h+rc.top], eax
0x18002ad7b  jnz     short loc_18002ADE0
0x18002ad7d  cmp     byte ptr [rbx+230h], 0
0x18002ad84  jnz     short loc_18002ADE0
0x18002ad86  mov     eax, [rbx+35Ch]
0x18002ad8c  mov     [rsp+78h+rc.right], eax
0x18002ad90  mov     rdx, [rdi]; pt
0x18002ad93  lea     rcx, [rsp+78h+rc]; lprc
0x18002ad98  call    cs:__imp_PtInRect
0x18002ad9e  test    eax, eax
0x18002ada0  jz      short loc_18002ADB3
0x18002ada2  mov     rbp, r12
0x18002ada5  mov     byte ptr [r15], 1
0x18002ada9  mov     r12, [rsp+78h+var_38]
0x18002adae  jmp     loc_18002AC7E
0x18002adb3  cmp     rbp, 1
0x18002adb7  jnz     short loc_18002ADBE
0x18002adb9  mov     ebp, 2
0x18002adbe  mov     byte ptr [r15], 1
0x18002adc2  mov     r12, [rsp+78h+var_38]
0x18002adc7  jmp     loc_18002AC7E
0x18002adcc  mov     ebp, 9
0x18002add1  jmp     loc_18002AD1F
0x18002add6  mov     ebp, 18h
0x18002addb  jmp     loc_18002AD1F
0x18002ade0  mov     eax, [rbx+354h]
0x18002ade6  mov     [rsp+78h+rc.left], eax
0x18002adea  jmp     short loc_18002AD90
0x18002adec  cmp     [rcx+228h], ebp
0x18002adf2  jnz     loc_18002AC5A
0x18002adf8  movzx   esi, bpl
0x18002adfc  jmp     loc_18002AC5D
0x18002ae01  mov     ebp, 17h
0x18002ae06  jmp     loc_18002AD1F
0x18002ae0b  mov     ecx, [rbx+278h]
0x18002ae11  cmp     [rdi+4], ecx
0x18002ae14  jg      loc_18002AD40
0x18002ae1a  mov     eax, [rbx+35Ch]
0x18002ae20  mov     edx, [rdi]
0x18002ae22  sub     eax, ecx
0x18002ae24  sub     eax, [rbx+354h]
0x18002ae2a  cmp     edx, eax
0x18002ae2c  jge     short loc_18002AE4E
0x18002ae2e  xor     ebp, ebp
0x18002ae30  cmp     edx, ecx
0x18002ae32  setle   bpl
0x18002ae36  add     rbp, 0Ch
0x18002ae3a  jmp     loc_18002AD40
0x18002ae3f  cmp     dword ptr [rdi+4], 0
0x18002ae43  jz      loc_18002AC9B
0x18002ae49  jmp     loc_18002AC7A
0x18002ae4e  mov     ebp, 0Eh
0x18002ae53  jmp     loc_18002AD40
```
