# CERT_MAP_RULE::~CERT_MAP_RULE(void)

- ea: `0x18000357c`
- end: `0x180003622`
- name: `??1CERT_MAP_RULE@@QEAA@XZ`
- size: `166`
- prototype: `void __fastcall(CERT_MAP_RULE *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003520`
- `0x1800041f0`

## callees

- `0x180001048`
- `0x18000357c`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x1800035c4`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800035c4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800035ba`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003602`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800035ba`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003602`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000361b`

## pseudocode

```c
void __fastcall CERT_MAP_RULE::~CERT_MAP_RULE(CERT_MAP_RULE *this)
{
  _QWORD **v2; // rsi
  _QWORD *v3; // rbx
  __int64 v4; // rax
  _QWORD *v5; // rcx
  int v6; // eax
  bool v7; // zf
  __int64 v8; // rdx
  _BYTE *v9; // rax

  v2 = (_QWORD **)((char *)this + 264);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    v4 = *v3;
    if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    STRU::~STRU((STRU *)(v3 + 12));
    STRA::~STRA((STRA *)(v3 + 3));
    operator delete(v3);
  }
  v6 = *((_DWORD *)this + 46);
  if ( v6 )
  {
    v7 = 2 * v6 == 0;
    v8 = (unsigned int)(2 * v6);
    v9 = (_BYTE *)*((_QWORD *)this + 21);
    if ( !v7 )
    {
      do
      {
        *v9++ = 0;
        --v8;
      }
      while ( v8 );
    }
  }
  STRU::~STRU((CERT_MAP_RULE *)((char *)this + 136));
  STRU::~STRU((CERT_MAP_RULE *)((char *)this + 16));
}

```

## disassembly

```asm
0x18000357c  mov     [rsp+arg_0], rbx
0x180003581  mov     [rsp+arg_8], rsi
0x180003586  push    rdi
0x180003587  sub     rsp, 20h
0x18000358b  mov     rdi, rcx
0x18000358e  lea     rsi, [rcx+108h]
0x180003595  mov     rbx, [rsi]
0x180003598  cmp     rbx, rsi
0x18000359b  jz      short loc_1800035DB
0x18000359d  mov     rax, [rbx]
0x1800035a0  cmp     [rax+8], rbx
0x1800035a4  jnz     short loc_1800035D4
0x1800035a6  mov     rcx, [rbx+8]
0x1800035aa  cmp     [rcx], rbx
0x1800035ad  jnz     short loc_1800035D4
0x1800035af  mov     [rcx], rax
0x1800035b2  mov     [rax+8], rcx
0x1800035b6  lea     rcx, [rbx+60h]
0x1800035ba  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800035c0  lea     rcx, [rbx+18h]
0x1800035c4  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800035ca  mov     rcx, rbx; Block
0x1800035cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800035d2  jmp     short loc_180003595
0x1800035d4  mov     ecx, 3
0x1800035d9  int     29h; Win8: RtlFailFast(ecx)
0x1800035db  lea     rcx, [rdi+88h]
0x1800035e2  mov     eax, [rcx+30h]
0x1800035e5  test    eax, eax
0x1800035e7  jz      short loc_180003602
0x1800035e9  add     eax, eax
0x1800035eb  mov     edx, eax
0x1800035ed  mov     rax, [rdi+0A8h]
0x1800035f4  jz      short loc_180003602
0x1800035f6  mov     byte ptr [rax], 0
0x1800035f9  inc     rax
0x1800035fc  sub     rdx, 1
0x180003600  jnz     short loc_1800035F6
0x180003602  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003608  lea     rcx, [rdi+10h]
0x18000360c  mov     rbx, [rsp+28h+arg_0]
0x180003611  mov     rsi, [rsp+28h+arg_8]
0x180003616  add     rsp, 20h
0x18000361a  pop     rdi
0x18000361b  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
