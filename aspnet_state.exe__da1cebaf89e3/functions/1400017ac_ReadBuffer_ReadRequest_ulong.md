# ReadBuffer::ReadRequest(ulong)

- ea: `0x1400017ac`
- end: `0x140001992`
- name: `?ReadRequest@ReadBuffer@@QEAAJK@Z`
- size: `486`
- prototype: `__int64 __fastcall(ReadBuffer *this, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140004410`

## callees

- `0x140001468`
- `0x1400017ac`
- `0x140003b78`
- `0x1400044f0`
- `0x140004f58`
- `0x140004fc8`
- `0x14000648e`
- `0x140006494`

## pseudocode

```c
__int64 __fastcall ReadBuffer::ReadRequest(ReadBuffer *this, int a2)
{
  unsigned int v2; // esi
  void *v3; // rbp
  int v5; // r8d
  void *v6; // rdx
  __int64 v7; // rcx
  bool v8; // sf
  char *v10; // rax
  int v11; // eax
  int v12; // ecx
  struct StateItem *v13; // rax
  int v14; // ebx
  int v15; // r8d
  int v16; // ecx
  int v17; // r8d
  int v18; // eax
  void *v19; // rax

  v2 = 0;
  v3 = 0;
  if ( !a2 )
  {
    v2 = -2147023670;
    goto LABEL_12;
  }
  if ( a2 == -1 )
  {
    v5 = *((_DWORD *)this + 4);
    v6 = (void *)*((_QWORD *)this + 1);
    goto LABEL_31;
  }
  v7 = *((_QWORD *)this + 9);
  if ( v7 )
  {
    v8 = a2 + *((_DWORD *)this + 20) < 0;
    *((_DWORD *)this + 20) += a2;
    if ( !v8 )
    {
      v5 = *((_DWORD *)this + 12) - *((_DWORD *)this + 20);
      if ( v5 <= 0 )
        goto LABEL_32;
      v6 = (void *)(*((int *)this + 20) + v7 + 8);
      goto LABEL_10;
    }
LABEL_7:
    v2 = -2147418113;
    goto LABEL_12;
  }
  v8 = a2 + *((_DWORD *)this + 5) < 0;
  *((_DWORD *)this + 5) += a2;
  if ( v8 )
    goto LABEL_7;
  *(_BYTE *)(*((int *)this + 5) + *((_QWORD *)this + 1)) = 0;
  if ( *((int *)this + 5) > 10240 )
  {
LABEL_15:
    v2 = -2147024809;
    goto LABEL_12;
  }
  v10 = strstr_0((const char *)(*((_QWORD *)this + 1) + *((int *)this + 6)), "\r\n\r\n");
  if ( !v10 )
  {
    v16 = *((_DWORD *)this + 5);
    v17 = *((_DWORD *)this + 4);
    v18 = v16 - 3;
    if ( *((_DWORD *)this + 6) >= v16 - 3 )
      v18 = *((_DWORD *)this + 6);
    *((_DWORD *)this + 6) = v18;
    if ( v16 == v17 )
    {
      v3 = (void *)*((_QWORD *)this + 1);
      *((_DWORD *)this + 4) = v17 + 1024;
      v19 = MemAlloc(v17 + 1025);
      *((_QWORD *)this + 1) = v19;
      if ( !v19 )
        goto LABEL_20;
      memcpy_0(v19, v3, *((_DWORD *)this + 5) + 1);
      v17 = *((_DWORD *)this + 4);
      v16 = *((_DWORD *)this + 5);
    }
    v5 = v17 - v16;
    v6 = (void *)(*((_QWORD *)this + 1) + v16);
LABEL_31:
    if ( v5 <= 0 )
      goto LABEL_32;
    goto LABEL_10;
  }
  v11 = (_DWORD)v10 - *((_DWORD *)this + 2) + 4;
  *((_DWORD *)this + 7) = v11;
  *((_DWORD *)this + 6) = v11;
  v2 = ReadBuffer::ParseHeader(this);
  if ( v2 )
    goto LABEL_12;
  v12 = *((_DWORD *)this + 12);
  if ( v12 <= 0 )
    goto LABEL_32;
  v13 = StateItem::Create(v12);
  *((_QWORD *)this + 9) = v13;
  if ( !v13 )
  {
LABEL_20:
    v2 = -2147024882;
    goto LABEL_12;
  }
  v14 = *((_DWORD *)this + 12);
  if ( *((_DWORD *)this + 5) - *((_DWORD *)this + 7) <= v14 )
    v14 = *((_DWORD *)this + 5) - *((_DWORD *)this + 7);
  memcpy_0((char *)v13 + 8, (const void *)(*((_QWORD *)this + 1) + *((int *)this + 7)), v14);
  v15 = *((_DWORD *)this + 12);
  *((_DWORD *)this + 6) += v14;
  v5 = v15 - v14;
  *((_DWORD *)this + 20) = v14;
  if ( v5 <= 0 )
  {
LABEL_32:
    if ( *((_DWORD *)this + 7) != 4 )
      goto LABEL_12;
    goto LABEL_15;
  }
  v6 = (void *)(v14 + *((_QWORD *)this + 9) + 8LL);
LABEL_10:
  v2 = Tracker::Read(*(Tracker **)this, v6, v5);
  if ( !v2 )
    v2 = 1;
LABEL_12:
  MemFree(v3);
  return v2;
}

```

## disassembly

```asm
0x1400017ac  mov     [rsp+arg_0], rbx
0x1400017b1  mov     [rsp+arg_8], rbp
0x1400017b6  mov     [rsp+arg_10], rsi
0x1400017bb  push    rdi
0x1400017bc  push    r14
0x1400017be  push    r15
0x1400017c0  sub     rsp, 20h
0x1400017c4  xor     esi, esi
0x1400017c6  xor     ebp, ebp
0x1400017c8  mov     rdi, rcx
0x1400017cb  test    edx, edx
0x1400017cd  jnz     short loc_1400017D6
0x1400017cf  mov     esi, 800704CAh
0x1400017d4  jmp     short loc_14000182F
0x1400017d6  mov     r15d, 1
0x1400017dc  cmp     edx, 0FFFFFFFFh
0x1400017df  jnz     short loc_1400017EE
0x1400017e1  mov     r8d, [rcx+10h]
0x1400017e5  mov     rdx, [rcx+8]
0x1400017e9  jmp     loc_14000197A
0x1400017ee  mov     rcx, [rcx+48h]
0x1400017f2  test    rcx, rcx
0x1400017f5  jz      short loc_140001852
0x1400017f7  add     [rdi+50h], edx
0x1400017fa  jns     short loc_140001803
0x1400017fc  mov     esi, 8000FFFFh
0x140001801  jmp     short loc_14000182F
0x140001803  mov     r8d, [rdi+30h]
0x140001807  sub     r8d, [rdi+50h]; int
0x14000180b  test    r8d, r8d
0x14000180e  jle     loc_140001983
0x140001814  movsxd  rax, dword ptr [rdi+50h]
0x140001818  lea     rdx, [rcx+8]
0x14000181c  add     rdx, rax; void *
0x14000181f  mov     rcx, [rdi]; this
0x140001822  call    ?Read@Tracker@@QEAAJPEAXH@Z; Tracker::Read(void *,int)
0x140001827  test    eax, eax
0x140001829  mov     esi, eax
0x14000182b  cmovz   esi, r15d
0x14000182f  mov     rcx, rbp; lpMem
0x140001832  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x140001837  mov     rbx, [rsp+38h+arg_0]
0x14000183c  mov     eax, esi
0x14000183e  mov     rsi, [rsp+38h+arg_10]
0x140001843  mov     rbp, [rsp+38h+arg_8]
0x140001848  add     rsp, 20h
0x14000184c  pop     r15
0x14000184e  pop     r14
0x140001850  pop     rdi
0x140001851  retn
0x140001852  add     [rdi+14h], edx
0x140001855  js      short loc_1400017FC
0x140001857  movsxd  rcx, dword ptr [rdi+14h]
0x14000185b  mov     rax, [rdi+8]
0x14000185f  mov     [rcx+rax], sil
0x140001863  cmp     dword ptr [rdi+14h], 2800h
0x14000186a  jle     short loc_140001873
0x14000186c  mov     esi, 80070057h
0x140001871  jmp     short loc_14000182F
0x140001873  movsxd  rcx, dword ptr [rdi+18h]
0x140001877  lea     rdx, asc_140007664; "\r\n\r\n"
0x14000187e  add     rcx, [rdi+8]; Str
0x140001882  call    strstr_0
0x140001887  test    rax, rax
0x14000188a  jz      loc_140001917
0x140001890  sub     eax, [rdi+8]
0x140001893  mov     rcx, rdi; this
0x140001896  add     eax, 4
0x140001899  mov     [rdi+1Ch], eax
0x14000189c  mov     [rdi+18h], eax
0x14000189f  call    ?ParseHeader@ReadBuffer@@AEAAJXZ; ReadBuffer::ParseHeader(void)
0x1400018a4  mov     esi, eax
0x1400018a6  test    eax, eax
0x1400018a8  jnz     short loc_14000182F
0x1400018aa  mov     ecx, [rdi+30h]; int
0x1400018ad  test    ecx, ecx
0x1400018af  jle     loc_140001983
0x1400018b5  call    ?Create@StateItem@@SAPEAV1@H@Z; StateItem::Create(int)
0x1400018ba  mov     [rdi+48h], rax
0x1400018be  mov     rcx, rax
0x1400018c1  test    rax, rax
0x1400018c4  jnz     short loc_1400018D0
0x1400018c6  mov     esi, 8007000Eh
0x1400018cb  jmp     loc_14000182F
0x1400018d0  mov     ebx, [rdi+30h]
0x1400018d3  mov     eax, [rdi+14h]
0x1400018d6  sub     eax, [rdi+1Ch]
0x1400018d9  movsxd  rdx, dword ptr [rdi+1Ch]
0x1400018dd  cmp     eax, ebx
0x1400018df  cmovle  ebx, eax
0x1400018e2  add     rdx, [rdi+8]; Src
0x1400018e6  movsxd  r14, ebx
0x1400018e9  add     rcx, 8; void *
0x1400018ed  mov     r8, r14; Size
0x1400018f0  call    memcpy_0
0x1400018f5  mov     r8d, [rdi+30h]
0x1400018f9  add     [rdi+18h], ebx
0x1400018fc  sub     r8d, ebx
0x1400018ff  mov     [rdi+50h], ebx
0x140001902  test    r8d, r8d
0x140001905  jle     short loc_140001983
0x140001907  mov     rdx, [rdi+48h]
0x14000190b  add     rdx, 8
0x14000190f  add     rdx, r14
0x140001912  jmp     loc_14000181F
0x140001917  mov     ecx, [rdi+14h]
0x14000191a  mov     r8d, [rdi+10h]
0x14000191e  lea     eax, [rcx-3]
0x140001921  cmp     [rdi+18h], eax
0x140001924  cmovge  eax, [rdi+18h]
0x140001928  mov     [rdi+18h], eax
0x14000192b  cmp     ecx, r8d
0x14000192e  jnz     short loc_140001970
0x140001930  mov     rbp, [rdi+8]
0x140001934  lea     eax, [r8+400h]
0x14000193b  mov     [rdi+10h], eax
0x14000193e  inc     eax
0x140001940  movsxd  rcx, eax; unsigned __int64
0x140001943  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x140001948  mov     [rdi+8], rax
0x14000194c  mov     rcx, rax; void *
0x14000194f  test    rax, rax
0x140001952  jz      loc_1400018C6
0x140001958  mov     eax, [rdi+14h]
0x14000195b  mov     rdx, rbp; Src
0x14000195e  add     eax, r15d
0x140001961  movsxd  r8, eax; Size
0x140001964  call    memcpy_0
0x140001969  mov     r8d, [rdi+10h]
0x14000196d  mov     ecx, [rdi+14h]
0x140001970  sub     r8d, ecx
0x140001973  movsxd  rdx, ecx
0x140001976  add     rdx, [rdi+8]
0x14000197a  test    r8d, r8d
0x14000197d  jg      loc_14000181F
0x140001983  cmp     dword ptr [rdi+1Ch], 4
0x140001987  jnz     loc_14000182F
0x14000198d  jmp     loc_14000186C
```
