# MagnifierExperienceHelper::SetMonitorRect(tagRECT const &)

- ea: `0x1800bd92c`
- end: `0x1800bd99b`
- name: `?SetMonitorRect@MagnifierExperienceHelper@@AEAAXAEBUtagRECT@@@Z`
- size: `111`
- prototype: `void __fastcall(MagnifierExperienceHelper *__hidden this, RECT *lprcSrc)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800bd238`
- `0x1800bd3c4`

## callees

- `0x1800bd92c`
- `0x1800bda40`

## import_xrefs

- `USER32!CopyRect` at `0x1800bd958`
- `USER32!CopyRect` at `0x1800bd958`
- `USER32!EqualRect` at `0x1800bd948`
- `USER32!EqualRect` at `0x1800bd948`

## pseudocode

```c
void __fastcall MagnifierExperienceHelper::SetMonitorRect(RECT *this, RECT *lprcSrc)
{
  struct tagRECT *v2; // rdi
  int v5; // eax

  v2 = this + 3;
  if ( !EqualRect(this + 3, lprcSrc) )
  {
    CopyRect(v2, lprcSrc);
    v5 = this[3].bottom - this[3].top;
    *(double *)&this[4].left = (double)(this[3].right - v2->left);
    *(double *)&this[4].right = (double)v5;
    MagnifierExperienceHelper::UpdateMagnifiedWindowParameters((MagnifierExperienceHelper *)this);
  }
}

```

## disassembly

```asm
0x1800bd92c  mov     [rsp+arg_0], rbx
0x1800bd931  mov     [rsp+arg_8], rsi
0x1800bd936  push    rdi
0x1800bd937  sub     rsp, 20h
0x1800bd93b  lea     rdi, [rcx+30h]
0x1800bd93f  mov     rbx, rcx
0x1800bd942  mov     rcx, rdi; lprc1
0x1800bd945  mov     rsi, rdx
0x1800bd948  call    cs:__imp_EqualRect
0x1800bd94e  test    eax, eax
0x1800bd950  jnz     short loc_1800BD98B
0x1800bd952  mov     rdx, rsi; lprcSrc
0x1800bd955  mov     rcx, rdi; lprcDst
0x1800bd958  call    cs:__imp_CopyRect
0x1800bd95e  mov     eax, [rbx+38h]
0x1800bd961  mov     rcx, rbx; this
0x1800bd964  sub     eax, [rdi]
0x1800bd966  movd    xmm0, eax
0x1800bd96a  mov     eax, [rbx+3Ch]
0x1800bd96d  sub     eax, [rbx+34h]
0x1800bd970  cvtdq2pd xmm0, xmm0
0x1800bd974  movsd   qword ptr [rbx+40h], xmm0
0x1800bd979  movd    xmm0, eax
0x1800bd97d  cvtdq2pd xmm0, xmm0
0x1800bd981  movsd   qword ptr [rbx+48h], xmm0
0x1800bd986  call    ?UpdateMagnifiedWindowParameters@MagnifierExperienceHelper@@AEAAXXZ; MagnifierExperienceHelper::UpdateMagnifiedWindowParameters(void)
0x1800bd98b  mov     rbx, [rsp+28h+arg_0]
0x1800bd990  mov     rsi, [rsp+28h+arg_8]
0x1800bd995  add     rsp, 20h
0x1800bd999  pop     rdi
0x1800bd99a  retn
```
