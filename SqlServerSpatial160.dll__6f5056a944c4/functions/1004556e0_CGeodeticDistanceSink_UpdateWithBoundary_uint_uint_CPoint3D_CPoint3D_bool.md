# CGeodeticDistanceSink::UpdateWithBoundary(uint,uint,CPoint3D &,CPoint3D &,bool)

- ea: `0x1004556e0`
- end: `0x100455818`
- name: `?UpdateWithBoundary@CGeodeticDistanceSink@@IEAAXIIAEAVCPoint3D@@0_N@Z`
- size: `312`
- prototype: `void __fastcall(CGeodeticDistanceSink *__hidden this, unsigned int, unsigned int, struct CPoint3D *, struct CPoint3D *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1004553d0`

## callees

- `0x100452fd0`
- `0x1004556e0`

## pseudocode

```c
void __fastcall CGeodeticDistanceSink::UpdateWithBoundary(
        CGeodeticDistanceSink *this,
        unsigned int a2,
        unsigned int a3,
        struct CPoint3D *a4,
        struct CPoint3D *a5,
        bool a6)
{
  __int64 v6; // rdi
  __int64 v8; // rsi
  _QWORD *v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // edx
  _BYTE v12[40]; // [rsp+20h] [rbp-28h] BYREF

  v6 = a3;
  v8 = a2;
  if ( a6
    || (CGeodeticPointEdgeDistance::Update(
          (CGeodeticDistanceSink *)((char *)this + 984),
          a4,
          a2,
          *((_DWORD **)this + a2 + 641)),
        *(double *)(*((_QWORD *)this + 655) + 88LL) < *(double *)(*((_QWORD *)this + 655) + 32LL)) )
  {
    if ( (CGeodeticDistanceSink *)((char *)this + 3784) == *((CGeodeticDistanceSink **)this + 641)
      || (CGeodeticDistanceSink *)((char *)this + 4456) == *((CGeodeticDistanceSink **)this + 642) )
    {
      *(_DWORD *)(*((_QWORD *)this + v6 + 641) + 244LL) = 0;
      while ( 1 )
      {
        v9 = (_QWORD *)(***((__int64 (__fastcall ****)(_QWORD, _BYTE *))this + v6 + 641))(
                         *((_QWORD *)this + v6 + 641),
                         v12);
        CGeodeticPointEdgeDistance::Update(
          (CGeodeticDistanceSink *)((char *)this + 984),
          v9,
          v8,
          *((_DWORD **)this + v8 + 641));
        if ( *(double *)(*((_QWORD *)this + 655) + 88LL) >= *(double *)(*((_QWORD *)this + 655) + 32LL) )
          break;
        v10 = *((_QWORD *)this + v6 + 641);
        v11 = *(_DWORD *)(v10 + 244);
        if ( v11 >= *(_DWORD *)(v10 + 240) - 1 )
          break;
        *(_DWORD *)(v10 + 244) = v11 + 1;
      }
    }
    else
    {
      CGeodeticPointEdgeDistance::Update(
        (CGeodeticDistanceSink *)((char *)this + 984),
        a5,
        v8,
        *((_DWORD **)this + v8 + 641));
    }
  }
}

```

## disassembly

```asm
0x1004556e0  mov     [rsp+arg_0], rbx
0x1004556e5  mov     [rsp+arg_8], rbp
0x1004556ea  mov     [rsp+arg_10], rsi
0x1004556ef  mov     [rsp+arg_18], rdi
0x1004556f4  push    r14
0x1004556f6  sub     rsp, 40h
0x1004556fa  cmp     [rsp+48h+arg_28], 0
0x1004556ff  mov     rax, r9
0x100455702  mov     edi, r8d
0x100455705  mov     rbx, rcx
0x100455708  mov     esi, edx
0x10045570a  jnz     short loc_100455739
0x10045570c  mov     r9, [rcx+rsi*8+1408h]
0x100455714  mov     r8d, esi
0x100455717  add     rcx, 3D8h; this
0x10045571e  mov     rdx, rax
0x100455721  call    ?Update@CGeodeticPointEdgeDistance@@QEAAXAEBVCPoint3D@@IPEAV?$CEdge@VCPoint3D@@N@@@Z; CGeodeticPointEdgeDistance::Update(CPoint3D const &,uint,CEdge<CPoint3D,double> *)
0x100455726  mov     rax, [rbx+1478h]
0x10045572d  movsd   xmm0, qword ptr [rax+58h]
0x100455732  comisd  xmm0, qword ptr [rax+20h]
0x100455737  jnb     short loc_100455775
0x100455739  lea     rax, [rbx+0EC8h]
0x100455740  cmp     rax, [rbx+1408h]
0x100455747  jz      short loc_100455790
0x100455749  lea     rax, [rbx+1168h]
0x100455750  cmp     rax, [rbx+1410h]
0x100455757  jz      short loc_100455790
0x100455759  mov     r9, [rbx+rsi*8+1408h]
0x100455761  lea     rcx, [rbx+3D8h]; this
0x100455768  mov     rdx, [rsp+48h+arg_20]
0x10045576d  mov     r8d, esi
0x100455770  call    ?Update@CGeodeticPointEdgeDistance@@QEAAXAEBVCPoint3D@@IPEAV?$CEdge@VCPoint3D@@N@@@Z; CGeodeticPointEdgeDistance::Update(CPoint3D const &,uint,CEdge<CPoint3D,double> *)
0x100455775  mov     rbx, [rsp+48h+arg_0]
0x10045577a  mov     rbp, [rsp+48h+arg_8]
0x10045577f  mov     rsi, [rsp+48h+arg_10]
0x100455784  mov     rdi, [rsp+48h+arg_18]
0x100455789  add     rsp, 40h
0x10045578d  pop     r14
0x10045578f  retn
0x100455790  mov     rax, [rbx+rdi*8+1408h]
0x100455798  mov     dword ptr [rax+0F4h], 0
0x1004557a2  nop     dword ptr [rax+00h]
0x1004557a6  nop     word ptr [rax+rax+00000000h]
0x1004557b0  mov     rcx, [rbx+rdi*8+1408h]
0x1004557b8  lea     rdx, [rsp+48h+var_28]
0x1004557bd  mov     rax, [rcx]
0x1004557c0  call    qword ptr [rax]
0x1004557c2  mov     r9, [rbx+rsi*8+1408h]
0x1004557ca  lea     rcx, [rbx+3D8h]; this
0x1004557d1  mov     rdx, rax
0x1004557d4  mov     r8d, esi
0x1004557d7  call    ?Update@CGeodeticPointEdgeDistance@@QEAAXAEBVCPoint3D@@IPEAV?$CEdge@VCPoint3D@@N@@@Z; CGeodeticPointEdgeDistance::Update(CPoint3D const &,uint,CEdge<CPoint3D,double> *)
0x1004557dc  mov     rax, [rbx+1478h]
0x1004557e3  movsd   xmm0, qword ptr [rax+58h]
0x1004557e8  comisd  xmm0, qword ptr [rax+20h]
0x1004557ed  jnb     short loc_100455775
0x1004557ef  mov     rcx, [rbx+rdi*8+1408h]
0x1004557f7  mov     eax, [rcx+0F0h]
0x1004557fd  mov     edx, [rcx+0F4h]
0x100455803  dec     eax
0x100455805  cmp     edx, eax
0x100455807  jnb     loc_100455775
0x10045580d  lea     eax, [rdx+1]
0x100455810  mov     [rcx+0F4h], eax
0x100455816  jmp     short loc_1004557B0
```
