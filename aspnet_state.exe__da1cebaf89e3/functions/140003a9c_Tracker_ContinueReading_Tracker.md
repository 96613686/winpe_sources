# Tracker::ContinueReading(Tracker *)

- ea: `0x140003a9c`
- end: `0x140003b75`
- name: `?ContinueReading@Tracker@@AEAAJPEAV1@@Z`
- size: `217`
- prototype: `__int64 __fastcall(Tracker *__hidden this, struct Tracker *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140003bb0`

## callees

- `0x1400013c4`
- `0x140003a9c`
- `0x140004410`
- `0x140004638`
- `0x140004f90`

## string_xrefs

- `0x140003b57`: `ContinueReading`

## pseudocode

```c
__int64 __fastcall Tracker::ContinueReading(Tracker *this, struct Tracker *a2)
{
  ReadBuffer *v4; // rax
  unsigned int v5; // edi
  unsigned int v7; // [rsp+30h] [rbp+8h] BYREF

  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 6);
  if ( *((_BYTE *)StateWebServer::s_pstweb + 75) )
  {
    *(_OWORD *)((char *)this + 120) = *(_OWORD *)((char *)a2 + 120);
    *(_OWORD *)((char *)this + 136) = *(_OWORD *)((char *)a2 + 136);
    *(_OWORD *)((char *)this + 152) = *(_OWORD *)((char *)a2 + 152);
    *((_QWORD *)this + 21) = *((_QWORD *)a2 + 21);
  }
  else
  {
    *(_OWORD *)((char *)this + 56) = *(_OWORD *)((char *)a2 + 56);
    *(_OWORD *)((char *)this + 72) = *(_OWORD *)((char *)a2 + 72);
  }
  *((_QWORD *)a2 + 6) = -1;
  v4 = (ReadBuffer *)MemAllocClear(0x58u);
  *((_QWORD *)this + 26) = v4;
  if ( v4 )
  {
    v5 = ReadBuffer::Init(v4, this, *((struct ReadBuffer **)a2 + 26), (int *)&v7);
    if ( !v5 )
      v5 = Tracker::ProcessReading((ReadBuffer **)this, 0, v7);
  }
  else
  {
    v5 = -2147024882;
  }
  Tracker::RecordProcessError(this, v5, L"ContinueReading");
  return v5;
}

```

## disassembly

```asm
0x140003a9c  mov     [rsp+arg_8], rbx
0x140003aa1  push    rdi
0x140003aa2  sub     rsp, 20h
0x140003aa6  mov     rax, [rdx+30h]
0x140003aaa  mov     rdi, rdx
0x140003aad  mov     [rcx+30h], rax
0x140003ab1  mov     rbx, rcx
0x140003ab4  mov     rax, cs:?s_pstweb@StateWebServer@@0PEAV1@EA; StateWebServer * StateWebServer::s_pstweb
0x140003abb  cmp     byte ptr [rax+4Bh], 0
0x140003abf  jz      short loc_140003AF7
0x140003ac1  movups  xmm0, xmmword ptr [rdx+78h]
0x140003ac5  movups  xmmword ptr [rcx+78h], xmm0
0x140003ac9  movups  xmm1, xmmword ptr [rdx+88h]
0x140003ad0  movups  xmmword ptr [rcx+88h], xmm1
0x140003ad7  movups  xmm0, xmmword ptr [rdx+98h]
0x140003ade  movups  xmmword ptr [rcx+98h], xmm0
0x140003ae5  movsd   xmm1, qword ptr [rdx+0A8h]
0x140003aed  movsd   qword ptr [rcx+0A8h], xmm1
0x140003af5  jmp     short loc_140003B07
0x140003af7  movups  xmm0, xmmword ptr [rdx+38h]
0x140003afb  movups  xmmword ptr [rcx+38h], xmm0
0x140003aff  movups  xmm1, xmmword ptr [rdx+48h]
0x140003b03  movups  xmmword ptr [rcx+48h], xmm1
0x140003b07  or      qword ptr [rdx+30h], 0FFFFFFFFFFFFFFFFh
0x140003b0c  mov     ecx, 58h ; 'X'; unsigned __int64
0x140003b11  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x140003b16  mov     [rbx+0D0h], rax
0x140003b1d  test    rax, rax
0x140003b20  jnz     short loc_140003B29
0x140003b22  mov     edi, 8007000Eh
0x140003b27  jmp     short loc_140003B57
0x140003b29  mov     r8, [rdi+0D0h]; struct ReadBuffer *
0x140003b30  lea     r9, [rsp+28h+arg_0]; int *
0x140003b35  mov     rdx, rbx; struct Tracker *
0x140003b38  mov     rcx, rax; this
0x140003b3b  call    ?Init@ReadBuffer@@QEAAJPEAVTracker@@PEAV1@PEAH@Z; ReadBuffer::Init(Tracker *,ReadBuffer *,int *)
0x140003b40  mov     edi, eax
0x140003b42  test    eax, eax
0x140003b44  jnz     short loc_140003B57
0x140003b46  mov     r8d, [rsp+28h+arg_0]; unsigned int
0x140003b4b  xor     edx, edx; int
0x140003b4d  mov     rcx, rbx; this
0x140003b50  call    ?ProcessReading@Tracker@@AEAAJJH@Z; Tracker::ProcessReading(long,int)
0x140003b55  mov     edi, eax
0x140003b57  lea     r8, aContinuereadin; "ContinueReading"
0x140003b5e  mov     edx, edi; int
0x140003b60  mov     rcx, rbx; this
0x140003b63  call    ?RecordProcessError@Tracker@@AEAAXJPEBG@Z; Tracker::RecordProcessError(long,ushort const *)
0x140003b68  mov     rbx, [rsp+28h+arg_8]
0x140003b6d  mov     eax, edi
0x140003b6f  add     rsp, 20h
0x140003b73  pop     rdi
0x140003b74  retn
```
