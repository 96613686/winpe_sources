# DHT::copy_to_image(void)

- ea: `0x1800326b0`
- end: `0x180032a44`
- name: `?copy_to_image@DHT@@QEAAXXZ`
- size: `916`
- prototype: `void __fastcall(DHT *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180032a50`

## callees

- `0x1800326b0`

## pseudocode

```c
void __fastcall DHT::copy_to_image(DHT *this)
{
  __int64 v1; // rax
  unsigned __int64 v2; // r14
  int v3; // r11d
  int v4; // ebp
  int v5; // r10d
  __int64 v6; // rsi
  unsigned __int64 v7; // r9
  __int64 v8; // rbx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // eax
  int v13; // edx
  __int64 v14; // r9
  unsigned __int64 v15; // rbx
  int v16; // eax
  int v17; // edx

  v1 = *((_QWORD *)this + 5);
  v2 = *(unsigned __int16 *)(v1 + 30);
  if ( *(_WORD *)(v1 + 28) )
  {
    v3 = 4;
    v4 = 0;
    while ( 1 )
    {
      v5 = 0;
      v6 = 0;
      if ( v2 >= 4 )
        break;
      if ( (_DWORD)v2 )
        goto LABEL_9;
LABEL_11:
      ++v3;
      v4 += v2;
      if ( v3 - 4 >= *(unsigned __int16 *)(*((_QWORD *)this + 5) + 28LL) )
        return;
    }
    v7 = ((v2 - 4) >> 2) + 1;
    v8 = 8LL * v4;
    v6 = 4 * v7;
    do
    {
      *(_WORD *)(v8 + *(_QWORD *)(*((_QWORD *)this + 5) + 8LL)) = (int)*(float *)(*((_QWORD *)this + 1)
                                                                                + 12
                                                                                * (v5 + *((_DWORD *)this + 1) * v3 + 4LL));
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v8 + 4) = (int)*(float *)(*((_QWORD *)this + 1)
                                                                                    + 12LL
                                                                                    * (v5 + *((_DWORD *)this + 1) * v3)
                                                                                    + 56);
      v9 = (int)*(float *)(*((_QWORD *)this + 1) + 12LL * (v5 + *((_DWORD *)this + 1) * v3) + 52);
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v8 + 6) = v9;
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v8 + 2) = v9;
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v8 + 8) = (int)*(float *)(*((_QWORD *)this + 1)
                                                                                    + 12
                                                                                    * (v5
                                                                                     + *((_DWORD *)this + 1) * v3
                                                                                     + 5LL));
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v8 + 12) = (int)*(float *)(*((_QWORD *)this + 1)
                                                                                     + 12LL
                                                                                     * (v5 + *((_DWORD *)this + 1) * v3)
                                                                                     + 68);
      v10 = (int)*(float *)(*((_QWORD *)this + 1) + 12LL * (v5 + *((_DWORD *)this + 1) * v3) + 64);
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v8 + 14) = v10;
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v8 + 10) = v10;
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v8 + 16) = (int)*(float *)(*((_QWORD *)this + 1)
                                                                                     + 12
                                                                                     * (v5
                                                                                      + *((_DWORD *)this + 1) * v3
                                                                                      + 6LL));
      v8 += 32;
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v8 - 12) = (int)*(float *)(*((_QWORD *)this + 1)
                                                                                     + 12LL
                                                                                     * (v5 + *((_DWORD *)this + 1) * v3)
                                                                                     + 80);
      v11 = (int)*(float *)(*((_QWORD *)this + 1) + 12LL * (v5 + *((_DWORD *)this + 1) * v3) + 76);
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v8 - 10) = v11;
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v8 - 14) = v11;
      *(_WORD *)(v8 + *(_QWORD *)(*((_QWORD *)this + 5) + 8LL) - 8) = (int)*(float *)(*((_QWORD *)this + 1)
                                                                                    + 12
                                                                                    * (v5
                                                                                     + *((_DWORD *)this + 1) * v3
                                                                                     + 7LL));
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v8 - 4) = (int)*(float *)(*((_QWORD *)this + 1)
                                                                                    + 12LL
                                                                                    * (v5 + *((_DWORD *)this + 1) * v3)
                                                                                    + 92);
      v12 = v5 + *((_DWORD *)this + 1) * v3;
      v5 += 4;
      v13 = (int)*(float *)(*((_QWORD *)this + 1) + 12LL * v12 + 88);
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v8 - 2) = v13;
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v8 - 6) = v13;
      --v7;
    }
    while ( v7 );
    if ( v6 >= (__int64)v2 )
      goto LABEL_11;
LABEL_9:
    v14 = 8 * (v6 + v4);
    v15 = v2 - v6;
    do
    {
      v14 += 8;
      *(_WORD *)(v14 + *(_QWORD *)(*((_QWORD *)this + 5) + 8LL) - 8) = (int)*(float *)(*((_QWORD *)this + 1)
                                                                                     + 12
                                                                                     * (v5
                                                                                      + *((_DWORD *)this + 1) * v3
                                                                                      + 4LL));
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v14 - 4) = (int)*(float *)(*((_QWORD *)this + 1)
                                                                                     + 12LL
                                                                                     * (v5 + *((_DWORD *)this + 1) * v3)
                                                                                     + 56);
      v16 = v5 + *((_DWORD *)this + 1) * v3;
      ++v5;
      v17 = (int)*(float *)(*((_QWORD *)this + 1) + 12LL * v16 + 52);
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v14 - 2) = v17;
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + v14 - 6) = v17;
      --v15;
    }
    while ( v15 );
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x1800326b0  push    r14
0x1800326b2  push    r15
0x1800326b4  mov     rax, [rcx+28h]
0x1800326b8  xor     r15d, r15d
0x1800326bb  mov     r8, rcx
0x1800326be  movzx   r14d, word ptr [rax+1Eh]
0x1800326c3  cmp     r15w, [rax+1Ch]
0x1800326c8  jnb     loc_180032A3F
0x1800326ce  mov     [rsp+10h+arg_0], rbx
0x1800326d3  mov     r11d, 4
0x1800326d9  mov     [rsp+10h+arg_8], rbp
0x1800326de  mov     ebp, r15d
0x1800326e1  mov     [rsp+10h+arg_10], rsi
0x1800326e6  mov     [rsp+10h+arg_18], rdi
0x1800326eb  nop     dword ptr [rax+rax+00h]
0x1800326f0  mov     r10d, r15d
0x1800326f3  mov     rsi, r15
0x1800326f6  cmp     r14, 4
0x1800326fa  jb      loc_18003295B
0x180032700  lea     r9, [r14-4]
0x180032704  movsxd  rax, ebp
0x180032707  shr     r9, 2
0x18003270b  inc     r9
0x18003270e  lea     rbx, ds:0[rax*8]
0x180032716  lea     rsi, ds:0[r9*4]
0x18003271e  xchg    ax, ax
0x180032720  mov     eax, r11d
0x180032723  imul    eax, [r8+4]
0x180032728  add     eax, r10d
0x18003272b  cdqe
0x18003272d  add     rax, 4
0x180032731  lea     rcx, [rax+rax*2]
0x180032735  mov     rax, [r8+8]
0x180032739  cvttss2si edx, dword ptr [rax+rcx*4]
0x18003273e  mov     rax, [r8+28h]
0x180032742  mov     rcx, [rax+8]
0x180032746  mov     eax, r11d
0x180032749  mov     [rbx+rcx], dx
0x18003274d  imul    eax, [r8+4]
0x180032752  add     eax, r10d
0x180032755  cdqe
0x180032757  lea     rcx, [rax+rax*2]
0x18003275b  mov     rax, [r8+8]
0x18003275f  cvttss2si edx, dword ptr [rax+rcx*4+38h]
0x180032765  mov     rax, [r8+28h]
0x180032769  mov     rcx, [rax+8]
0x18003276d  mov     eax, r11d
0x180032770  mov     [rcx+rbx+4], dx
0x180032775  imul    eax, [r8+4]
0x18003277a  add     eax, r10d
0x18003277d  cdqe
0x18003277f  lea     rcx, [rax+rax*2]
0x180032783  mov     rax, [r8+8]
0x180032787  cvttss2si edx, dword ptr [rax+rcx*4+34h]
0x18003278d  mov     rax, [r8+28h]
0x180032791  mov     rcx, [rax+8]
0x180032795  mov     [rcx+rbx+6], dx
0x18003279a  mov     rax, [r8+28h]
0x18003279e  mov     rcx, [rax+8]
0x1800327a2  mov     eax, r11d
0x1800327a5  mov     [rcx+rbx+2], dx
0x1800327aa  imul    eax, [r8+4]
0x1800327af  add     eax, r10d
0x1800327b2  cdqe
0x1800327b4  add     rax, 5
0x1800327b8  lea     rcx, [rax+rax*2]
0x1800327bc  mov     rax, [r8+8]
0x1800327c0  cvttss2si edx, dword ptr [rax+rcx*4]
0x1800327c5  mov     rax, [r8+28h]
0x1800327c9  mov     rcx, [rax+8]
0x1800327cd  mov     eax, r11d
0x1800327d0  mov     [rcx+rbx+8], dx
0x1800327d5  imul    eax, [r8+4]
0x1800327da  add     eax, r10d
0x1800327dd  cdqe
0x1800327df  lea     rcx, [rax+rax*2]
0x1800327e3  mov     rax, [r8+8]
0x1800327e7  cvttss2si edx, dword ptr [rax+rcx*4+44h]
0x1800327ed  mov     rax, [r8+28h]
0x1800327f1  mov     rcx, [rax+8]
0x1800327f5  mov     eax, r11d
0x1800327f8  mov     [rcx+rbx+0Ch], dx
0x1800327fd  imul    eax, [r8+4]
0x180032802  add     eax, r10d
0x180032805  cdqe
0x180032807  lea     rcx, [rax+rax*2]
0x18003280b  mov     rax, [r8+8]
0x18003280f  cvttss2si edx, dword ptr [rax+rcx*4+40h]
0x180032815  mov     rax, [r8+28h]
0x180032819  mov     rcx, [rax+8]
0x18003281d  mov     [rcx+rbx+0Eh], dx
0x180032822  mov     rax, [r8+28h]
0x180032826  mov     rcx, [rax+8]
0x18003282a  mov     eax, r11d
0x18003282d  mov     [rcx+rbx+0Ah], dx
0x180032832  imul    eax, [r8+4]
0x180032837  add     eax, r10d
0x18003283a  cdqe
0x18003283c  add     rax, 6
0x180032840  lea     rcx, [rax+rax*2]
0x180032844  mov     rax, [r8+8]
0x180032848  cvttss2si edx, dword ptr [rax+rcx*4]
0x18003284d  mov     rax, [r8+28h]
0x180032851  mov     rcx, [rax+8]
0x180032855  mov     eax, r11d
0x180032858  mov     [rcx+rbx+10h], dx
0x18003285d  imul    eax, [r8+4]
0x180032862  add     eax, r10d
0x180032865  lea     rbx, [rbx+20h]
0x180032869  cdqe
0x18003286b  lea     rcx, [rax+rax*2]
0x18003286f  mov     rax, [r8+8]
0x180032873  cvttss2si edx, dword ptr [rax+rcx*4+50h]
0x180032879  mov     rax, [r8+28h]
0x18003287d  mov     rcx, [rax+8]
0x180032881  mov     eax, r11d
0x180032884  mov     [rcx+rbx-0Ch], dx
0x180032889  imul    eax, [r8+4]
0x18003288e  add     eax, r10d
0x180032891  cdqe
0x180032893  lea     rcx, [rax+rax*2]
0x180032897  mov     rax, [r8+8]
0x18003289b  cvttss2si edx, dword ptr [rax+rcx*4+4Ch]
0x1800328a1  mov     rax, [r8+28h]
0x1800328a5  mov     rcx, [rax+8]
0x1800328a9  mov     [rcx+rbx-0Ah], dx
0x1800328ae  mov     rax, [r8+28h]
0x1800328b2  mov     rcx, [rax+8]
0x1800328b6  mov     eax, r11d
0x1800328b9  mov     [rcx+rbx-0Eh], dx
0x1800328be  imul    eax, [r8+4]
0x1800328c3  add     eax, r10d
0x1800328c6  cdqe
0x1800328c8  add     rax, 7
0x1800328cc  lea     rcx, [rax+rax*2]
0x1800328d0  mov     rax, [r8+8]
0x1800328d4  cvttss2si edx, dword ptr [rax+rcx*4]
0x1800328d9  mov     rax, [r8+28h]
0x1800328dd  mov     rcx, [rax+8]
0x1800328e1  mov     eax, r11d
0x1800328e4  mov     [rbx+rcx-8], dx
0x1800328e9  imul    eax, [r8+4]
0x1800328ee  add     eax, r10d
0x1800328f1  cdqe
0x1800328f3  lea     rcx, [rax+rax*2]
0x1800328f7  mov     rax, [r8+8]
0x1800328fb  cvttss2si edx, dword ptr [rax+rcx*4+5Ch]
0x180032901  mov     rax, [r8+28h]
0x180032905  mov     rcx, [rax+8]
0x180032909  mov     eax, r11d
0x18003290c  mov     [rcx+rbx-4], dx
0x180032911  imul    eax, [r8+4]
0x180032916  add     eax, r10d
0x180032919  add     r10d, 4
0x18003291d  cdqe
0x18003291f  lea     rcx, [rax+rax*2]
0x180032923  mov     rax, [r8+8]
0x180032927  cvttss2si edx, dword ptr [rax+rcx*4+58h]
0x18003292d  mov     rax, [r8+28h]
0x180032931  mov     rcx, [rax+8]
0x180032935  mov     [rcx+rbx-2], dx
0x18003293a  mov     rax, [r8+28h]
0x18003293e  mov     rcx, [rax+8]
0x180032942  mov     [rcx+rbx-6], dx
0x180032947  sub     r9, 1
0x18003294b  jnz     loc_180032720
0x180032951  cmp     rsi, r14
0x180032954  jl      short loc_180032964
0x180032956  jmp     loc_180032A11
0x18003295b  test    r14d, r14d
0x18003295e  jz      loc_180032A11
0x180032964  movsxd  r9, ebp
0x180032967  mov     rbx, r14
0x18003296a  add     r9, rsi
0x18003296d  shl     r9, 3
0x180032971  sub     rbx, rsi
0x180032974  mov     eax, r11d
0x180032977  lea     r9, [r9+8]
0x18003297b  imul    eax, [r8+4]
0x180032980  add     eax, r10d
0x180032983  cdqe
0x180032985  add     rax, 4
0x180032989  lea     rcx, [rax+rax*2]
0x18003298d  mov     rax, [r8+8]
0x180032991  cvttss2si edx, dword ptr [rax+rcx*4]
0x180032996  mov     rax, [r8+28h]
0x18003299a  mov     rcx, [rax+8]
0x18003299e  mov     eax, r11d
0x1800329a1  mov     [r9+rcx-8], dx
0x1800329a7  imul    eax, [r8+4]
0x1800329ac  add     eax, r10d
0x1800329af  cdqe
0x1800329b1  lea     rcx, [rax+rax*2]
0x1800329b5  mov     rax, [r8+8]
0x1800329b9  cvttss2si edx, dword ptr [rax+rcx*4+38h]
0x1800329bf  mov     rax, [r8+28h]
0x1800329c3  mov     rcx, [rax+8]
0x1800329c7  mov     eax, r11d
0x1800329ca  mov     [rcx+r9-4], dx
0x1800329d0  imul    eax, [r8+4]
0x1800329d5  add     eax, r10d
0x1800329d8  inc     r10d
0x1800329db  cdqe
0x1800329dd  lea     rcx, [rax+rax*2]
0x1800329e1  mov     rax, [r8+8]
0x1800329e5  cvttss2si edx, dword ptr [rax+rcx*4+34h]
0x1800329eb  mov     rax, [r8+28h]
0x1800329ef  mov     rcx, [rax+8]
0x1800329f3  mov     [rcx+r9-2], dx
0x1800329f9  mov     rax, [r8+28h]
0x1800329fd  mov     rcx, [rax+8]
0x180032a01  mov     [rcx+r9-6], dx
0x180032a07  sub     rbx, 1
0x180032a0b  jnz     loc_180032974
0x180032a11  mov     rax, [r8+28h]
0x180032a15  inc     r11d
0x180032a18  add     ebp, r14d
0x180032a1b  movzx   ecx, word ptr [rax+1Ch]
0x180032a1f  lea     eax, [r11-4]
0x180032a23  cmp     eax, ecx
0x180032a25  jl      loc_1800326F0
0x180032a2b  mov     rdi, [rsp+10h+arg_18]
0x180032a30  mov     rsi, [rsp+10h+arg_10]
0x180032a35  mov     rbp, [rsp+10h+arg_8]
0x180032a3a  mov     rbx, [rsp+10h+arg_0]
0x180032a3f  pop     r15
0x180032a41  pop     r14
0x180032a43  retn
```
