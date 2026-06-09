# CGeodeticDistanceSink::UpdateWithPoint(uint,CPoint3D *)

- ea: `0x100455310`
- end: `0x1004553c0`
- name: `?UpdateWithPoint@CGeodeticDistanceSink@@IEAAXIPEAVCPoint3D@@@Z`
- size: `176`
- prototype: `void(CGeodeticDistanceSink *__hidden this, unsigned int, struct CPoint3D *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x100455820`
- `0x100456240`

## callees

- `0x10044dfc0`
- `0x100452fd0`
- `0x100455310`
- `0x100457d00`
- `0x100458050`
- `0x100467f10`

## pseudocode

```c
void __fastcall CGeodeticDistanceSink::UpdateWithPoint(CGeodeticDistanceSink *this, int a2, struct CPoint3D *a3)
{
  const struct CPoint3D *v5; // r8
  char *v6; // rsi
  char v7; // al

  if ( a2 == 1 )
  {
    CGeodeticPointPointDistance::Update(
      (CGeodeticDistanceSink *)((char *)this + 8),
      a3,
      (CGeodeticDistanceSink *)((char *)this + 5144));
  }
  else
  {
    v5 = (struct CPoint3D *)((char *)a3 + 24);
    if ( a2 == 2 )
    {
      v6 = (char *)this + 3256;
      v7 = CLinearEdge<CPoint3D,double>::Set((char *)this + 3256, a3, v5);
    }
    else
    {
      v6 = (char *)this + 3784;
      CGeodeticCircularArc::Construct(
        (CGeodeticDistanceSink *)((char *)this + 4056),
        a3,
        v5,
        *((double *)this + 475) / *((double *)this + 474));
      v7 = CCircularEdge::Set((CCircularEdge *)v6, (const struct CGeodeticCircularArc *)(v6 + 272));
    }
    if ( v7 )
    {
      *((_QWORD *)this + 641) = v6;
      CGeodeticPointEdgeDistance::Update((CGeodeticDistanceSink *)((char *)this + 984), (_QWORD *)this + 643, 0, v6);
    }
  }
}

```

## disassembly

```asm
0x100455310  push    rdi
0x100455312  sub     rsp, 20h
0x100455316  mov     rax, r8
0x100455319  mov     rdi, rcx
0x10045531c  cmp     edx, 1
0x10045531f  jnz     short loc_100455339
0x100455321  lea     r8, [rcx+1418h]; struct CPoint3D *
0x100455328  mov     rdx, rax; struct CPoint3D *
0x10045532b  add     rcx, 8; this
0x10045532f  add     rsp, 20h
0x100455333  pop     rdi
0x100455334  jmp     ?Update@CGeodeticPointPointDistance@@QEAAXAEBVCPoint3D@@0@Z; CGeodeticPointPointDistance::Update(CPoint3D const &,CPoint3D const &)
0x100455339  add     r8, 18h; struct CPoint3D *
0x10045533d  mov     [rsp+28h+arg_8], rsi
0x100455342  cmp     edx, 2
0x100455345  mov     rdx, rax; struct CPoint3D *
0x100455348  jnz     short loc_10045535B
0x10045534a  lea     rsi, [rcx+0CB8h]
0x100455351  mov     rcx, rsi
0x100455354  call    ?Set@?$CLinearEdge@VCPoint3D@@N@@QEAA_NAEBVCPoint3D@@0@Z; CLinearEdge<CPoint3D,double>::Set(CPoint3D const &,CPoint3D const &)
0x100455359  jmp     short loc_100455391
0x10045535b  lea     rsi, [rcx+0EC8h]
0x100455362  mov     [rsp+28h+arg_0], rbx
0x100455367  movsd   xmm3, qword ptr [rsi+10h]
0x10045536c  lea     rcx, [rsi+110h]; this
0x100455373  divsd   xmm3, qword ptr [rsi+8]; double
0x100455378  call    ?Construct@CGeodeticCircularArc@@QEAAXAEBVCPoint3D@@PEBV2@N@Z; CGeodeticCircularArc::Construct(CPoint3D const &,CPoint3D const *,double)
0x10045537d  lea     rdx, [rsi+110h]; struct CGeodeticCircularArc *
0x100455384  mov     rcx, rsi; this
0x100455387  call    ?Set@CCircularEdge@@QEAA_NAEBVCGeodeticCircularArc@@@Z; CCircularEdge::Set(CGeodeticCircularArc const &)
0x10045538c  mov     rbx, [rsp+28h+arg_0]
0x100455391  test    al, al
0x100455393  jz      short loc_1004553B5
0x100455395  lea     rdx, [rdi+1418h]
0x10045539c  mov     [rdi+1408h], rsi
0x1004553a3  lea     rcx, [rdi+3D8h]; this
0x1004553aa  mov     r9, rsi
0x1004553ad  xor     r8d, r8d
0x1004553b0  call    ?Update@CGeodeticPointEdgeDistance@@QEAAXAEBVCPoint3D@@IPEAV?$CEdge@VCPoint3D@@N@@@Z; CGeodeticPointEdgeDistance::Update(CPoint3D const &,uint,CEdge<CPoint3D,double> *)
0x1004553b5  mov     rsi, [rsp+28h+arg_8]
0x1004553ba  add     rsp, 20h
0x1004553be  pop     rdi
0x1004553bf  retn
```
