# CResponseBuffer::Write(char *,ulong,int,int)

- ea: `0x180019090`
- end: `0x1800195ea`
- name: `?Write@CResponseBuffer@@QEAAJPEADKHH@Z`
- size: `1370`
- prototype: `__int64 __fastcall(CResponseBuffer *__hidden this, char *, unsigned int, int, int)`
- caller_count: `11`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000ca50`
- `0x180018de0`
- `0x180019090`
- `0x1800511d0`
- `0x180051460`
- `0x180051934`
- `0x1800520c8`
- `0x180052ab0`
- `0x180052fe0`
- `0x18005316c`
- `0x180053428`

## callees

- `0x180019090`
- `0x180023d6e`
- `0x180023dd0`
- `0x1800406b0`
- `0x180050da4`
- `0x180050f08`
- `0x180051764`
- `0x180051fa0`

## import_xrefs

- `msvcrt!_itoa_s` at `0x180019151`
- `msvcrt!_itoa_s` at `0x180019151`
- `KERNEL32!HeapReAlloc` at `0x18001942a`
- `KERNEL32!HeapReAlloc` at `0x18001942a`
- `KERNEL32!HeapAlloc` at `0x18001941b`
- `KERNEL32!HeapAlloc` at `0x18001941b`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18001947c`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18001947c`

## pseudocode

```c
__int64 __fastcall CResponseBuffer::Write(CResponseBuffer *this, char *a2, unsigned int a3, int a4, int a5)
{
  size_t v6; // rbp
  char *v7; // r9
  unsigned int v10; // eax
  int v11; // edx
  __int64 v12; // r12
  _DWORD *v13; // r14
  unsigned int v14; // ecx
  volatile signed __int32 *v15; // rax
  volatile signed __int32 *v16; // rax
  void *v17; // rbx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // r15d
  int v22; // ecx
  unsigned int v23; // r15d
  unsigned int v24; // ebx
  unsigned int v25; // eax
  _QWORD *v26; // rax
  unsigned int v27; // ebx
  void *v28; // rax
  int v29; // eax
  __int64 v30; // rdx
  unsigned int v31; // ebx
  void *v32; // r15
  unsigned int v33; // edx
  __int64 v34; // rcx
  _DWORD *v35; // rax
  unsigned int v36; // eax
  __int64 v37; // rcx
  char *v38; // rax
  char *v39; // rax
  char *Src; // [rsp+30h] [rbp-68h]
  char Buffer[16]; // [rsp+40h] [rbp-58h] BYREF

  v6 = a3;
  v7 = a2;
  Src = a2;
  if ( !a3 && a4 )
    return 0;
  v10 = *((_DWORD *)this + 7);
  if ( v10 + a3 >= v10 )
  {
    if ( v10 + a3 > *((_DWORD *)this + 528) )
    {
      CResponseBuffer::Clear(this);
      ExceptionId(&IID_IResponse, 0x1770u, 0x76u, 0);
      return (unsigned int)-2147467259;
    }
    LODWORD(v12) = 0;
    if ( a4 )
    {
      if ( _itoa_s(a3, Buffer, 0xFu, 16) )
        return (unsigned int)-2147418113;
      v12 = -1;
      do
        ++v12;
      while ( Buffer[v12] );
      *(_WORD *)&Buffer[(int)v12] = 2573;
      v11 = CResponseBuffer::Write(this, Buffer, (int)v12 + 2, 0, 0);
      if ( v11 < 0 )
        return (unsigned int)v11;
      v7 = Src;
    }
    v13 = (_DWORD *)((char *)this + 2108);
    if ( *((_DWORD *)this + 525) )
      v14 = 2048 - *v13;
    else
      v14 = 0;
    if ( dword_18007E3F8 )
    {
      if ( !(_DWORD)v6 )
        _InterlockedIncrement(&dword_18007E384);
      if ( !a5 )
      {
        _InterlockedIncrement((volatile signed __int32 *)&sRespVecStats);
        goto LABEL_49;
      }
      if ( (unsigned int)v6 > 0x10 )
      {
        if ( (unsigned int)v6 > 0x20 )
        {
          if ( (unsigned int)v6 > 0x30 )
          {
            if ( (unsigned int)v6 > 0x40 )
            {
              if ( (unsigned int)v6 > 0x80 )
              {
                if ( (unsigned int)v6 > 0x100 )
                {
                  if ( (unsigned int)v6 > 0x200 )
                  {
                    if ( (unsigned int)v6 > 0x400 )
                    {
                      if ( (unsigned int)v6 > 0x800 )
                      {
                        if ( (unsigned int)v6 > 0x1000 )
                        {
                          if ( (unsigned int)v6 > 0x2000 )
                          {
                            v15 = &dword_18007E3BC;
                            if ( (unsigned int)v6 > 0x4000 )
                              v15 = (volatile signed __int32 *)byte_18007E3C0;
                          }
                          else
                          {
                            v15 = (volatile signed __int32 *)byte_18007E3B8;
                          }
                        }
                        else
                        {
                          v15 = &dword_18007E3B4;
                        }
                      }
                      else
                      {
                        v15 = (volatile signed __int32 *)byte_18007E3B0;
                      }
                    }
                    else
                    {
                      v15 = &dword_18007E3AC;
                    }
                  }
                  else
                  {
                    v15 = (volatile signed __int32 *)byte_18007E3A8;
                  }
                }
                else
                {
                  v15 = &dword_18007E3A4;
                }
              }
              else
              {
                v15 = (volatile signed __int32 *)byte_18007E3A0;
              }
            }
            else
            {
              v15 = &dword_18007E39C;
            }
          }
          else
          {
            v15 = (volatile signed __int32 *)byte_18007E398;
          }
        }
        else
        {
          v15 = &dword_18007E394;
        }
      }
      else
      {
        v15 = (volatile signed __int32 *)byte_18007E390;
      }
      _InterlockedIncrement(v15);
      v16 = &dword_18007E38C;
      if ( (unsigned int)v6 <= 0xC0 )
        v16 = (volatile signed __int32 *)byte_18007E388;
      _InterlockedAdd(v16, v6);
    }
    else if ( !a5 )
    {
      goto LABEL_49;
    }
    if ( (unsigned int)v6 > 0xC0 )
    {
      v19 = *((_DWORD *)this + 6);
      if ( (v19 & 1) != 0 )
      {
        ++*((_DWORD *)this + 5);
        *((_DWORD *)this + 6) = v19 & 0xFFFFFFFE;
      }
      v11 = CResponseVector::Append((CResponseBuffer *)((char *)this + 8), v7, v6);
      v20 = *((_DWORD *)this + 6);
      if ( (v20 & 1) != 0 )
      {
        ++*((_DWORD *)this + 5);
        *((_DWORD *)this + 6) = v20 & 0xFFFFFFFE;
      }
      if ( v11 >= 0 )
        v11 = CResponseBufferSet::AddTemplateToArray(*(CResponseBufferSet **)this);
      goto LABEL_51;
    }
LABEL_49:
    if ( (unsigned int)v6 <= v14 )
    {
      v17 = (void *)((unsigned int)*v13 + *(_QWORD *)(*((_QWORD *)this + 260) + 8LL * *((unsigned int *)this + 526)));
      memcpy_0(v17, v7, v6);
      v18 = CResponseVector::Append((CResponseBuffer *)((char *)this + 8), (char *)v17, v6);
      *v13 += v6;
      v11 = v18;
LABEL_51:
      if ( a4 )
        return (unsigned int)CResponseBuffer::Write(this, &Buffer[(int)v12], 2u, 0, 0);
      return (unsigned int)v11;
    }
    v21 = v6 - v14;
    v22 = *((_DWORD *)this + 524);
    v23 = (unsigned int)(v21 + 2047) >> 11;
    if ( v23 > v22 - *((_DWORD *)this + 525) )
    {
      v24 = v23 + v22 + 256;
      v25 = 8 * v24;
      if ( 8 * v24 < v24 || v25 < 8 )
        return (unsigned int)-2147024882;
      v26 = v22 == 1 ? HeapAlloc(g_hDenaliHeap, 0, v25) : HeapReAlloc(g_hDenaliHeap, 0, *((LPVOID *)this + 260), v25);
      if ( !v26 )
        return (unsigned int)-2147024882;
      if ( *((_DWORD *)this + 524) == 1 )
        *v26 = **((_QWORD **)this + 260);
      *((_QWORD *)this + 260) = v26;
      *((_DWORD *)this + 524) = v24;
    }
    v27 = 0;
    if ( !v23 )
    {
LABEL_76:
      v11 = 0;
      if ( (_DWORD)v6 )
      {
        while ( 1 )
        {
          if ( *v13 == 2048 )
          {
            ++*((_DWORD *)this + 526);
            *v13 = 0;
            v29 = *((_DWORD *)this + 6);
            if ( (v29 & 1) != 0 )
            {
              ++*((_DWORD *)this + 5);
              *((_DWORD *)this + 6) = v29 & 0xFFFFFFFE;
            }
          }
          v30 = (unsigned int)*v13;
          v31 = 2048 - v30;
          if ( (unsigned int)v6 < 2048 - (int)v30 )
            v31 = v6;
          v32 = (void *)(v30 + *(_QWORD *)(*((_QWORD *)this + 260) + 8LL * *((unsigned int *)this + 526)));
          memcpy_0(v32, Src, v31);
          if ( v31 )
          {
            v33 = *((_DWORD *)this + 5);
            if ( (*((_BYTE *)this + 24) & 1) != 0 )
            {
              v34 = 16LL * v33;
              if ( v33 >= 0x80 )
                v35 = (_DWORD *)(v34 + *((_QWORD *)this + 1) - 2048LL);
              else
                v35 = (_DWORD *)((char *)this + v34 + 32);
              *v35 += v31;
            }
            else
            {
              if ( v33 >= *((_DWORD *)this + 4) + 128 )
              {
                v11 = CResponseVector::GrowVector((CResponseBuffer *)((char *)this + 8));
                if ( v11 < 0 )
                {
                  *v13 += v31;
                  return (unsigned int)v11;
                }
              }
              v36 = *((_DWORD *)this + 5);
              *((_DWORD *)this + 6) |= 1u;
              v37 = 16LL * v36;
              if ( v36 >= 0x80 )
                v38 = (char *)(*((_QWORD *)this + 1) - 2048LL);
              else
                v38 = (char *)this + 32;
              v39 = &v38[v37];
              *(_DWORD *)v39 = v31;
              *((_QWORD *)v39 + 1) = v32;
            }
            *((_DWORD *)this + 7) += v31;
          }
          *v13 += v31;
          v11 = 0;
          Src += v31;
          LODWORD(v6) = v6 - v31;
          if ( !(_DWORD)v6 )
            goto LABEL_51;
        }
      }
      goto LABEL_51;
    }
    while ( g_pachResponseBuffer )
    {
      v28 = ALLOC_CACHE_HANDLER::Alloc(g_pachResponseBuffer);
      if ( !v28 )
        break;
      ++v27;
      *(_QWORD *)(*((_QWORD *)this + 260) + 8LL * (unsigned int)(*((_DWORD *)this + 525))++) = v28;
      if ( v27 >= v23 )
        goto LABEL_76;
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)-2147024362;
}

```

## disassembly

```asm
0x180019090  push    rbp
0x180019092  push    rdi
0x180019093  sub     rsp, 88h
0x18001909a  mov     rax, cs:__security_cookie
0x1800190a1  xor     rax, rsp
0x1800190a4  mov     [rsp+98h+var_48], rax
0x1800190a9  mov     [rsp+98h+var_60], r9d
0x1800190ae  mov     r10d, r9d
0x1800190b1  mov     ebp, r8d
0x1800190b4  mov     r9, rdx
0x1800190b7  mov     [rsp+98h+Src], rdx
0x1800190bc  mov     rdi, rcx
0x1800190bf  test    r8d, r8d
0x1800190c2  jnz     short loc_1800190D0
0x1800190c4  test    r10d, r10d
0x1800190c7  jz      short loc_1800190D0
0x1800190c9  xor     eax, eax
0x1800190cb  jmp     loc_1800195D3
0x1800190d0  mov     eax, [rcx+1Ch]
0x1800190d3  mov     [rsp+98h+arg_18], rbx
0x1800190db  mov     [rsp+98h+var_18], rsi
0x1800190e3  mov     [rsp+98h+var_20], r12
0x1800190e8  mov     [rsp+98h+var_28], r13
0x1800190ed  lea     ecx, [rax+rbp]
0x1800190f0  mov     [rsp+98h+var_30], r14
0x1800190f5  mov     [rsp+98h+var_38], r15
0x1800190fa  cmp     ecx, eax
0x1800190fc  jb      loc_1800195A8
0x180019102  cmp     ecx, [rdi+840h]
0x180019108  jbe     short loc_180019136
0x18001910a  mov     rcx, rdi; this
0x18001910d  call    ?Clear@CResponseBuffer@@QEAAJXZ; CResponseBuffer::Clear(void)
0x180019112  xor     r9d, r9d; int
0x180019115  lea     rcx, IID_IResponse; struct _GUID *
0x18001911c  mov     edx, 1770h; unsigned int
0x180019121  mov     r8d, 76h ; 'v'; unsigned int
0x180019127  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x18001912c  mov     edx, 80004005h
0x180019131  jmp     loc_1800195AD
0x180019136  xor     r12d, r12d
0x180019139  test    r10d, r10d
0x18001913c  jz      short loc_1800191B1
0x18001913e  mov     r9d, 10h; Radix
0x180019144  lea     rdx, [rsp+98h+Buffer]; Buffer
0x180019149  mov     r8d, 0Fh; BufferCount
0x18001914f  mov     ecx, ebp; Value
0x180019151  call    cs:__imp__itoa_s
0x180019157  test    eax, eax
0x180019159  jz      short loc_180019165
0x18001915b  mov     edx, 8000FFFFh
0x180019160  jmp     loc_1800195AD
0x180019165  lea     rax, [rsp+98h+Buffer]
0x18001916a  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180019171  inc     r12
0x180019174  cmp     byte ptr [rax+r12], 0
0x180019179  jnz     short loc_180019171
0x18001917b  movsxd  rax, r12d
0x18001917e  lea     r8d, [r12+2]; unsigned int
0x180019183  xor     r9d, r9d; int
0x180019186  mov     [rsp+98h+var_78], 0; int
0x18001918e  lea     rdx, [rsp+98h+Buffer]; char *
0x180019193  mov     rcx, rdi; this
0x180019196  mov     word ptr [rsp+rax+98h+Buffer], 0A0Dh
0x18001919d  call    ?Write@CResponseBuffer@@QEAAJPEADKHH@Z; CResponseBuffer::Write(char *,ulong,int,int)
0x1800191a2  mov     edx, eax
0x1800191a4  test    eax, eax
0x1800191a6  js      loc_1800195AD
0x1800191ac  mov     r9, [rsp+98h+Src]
0x1800191b1  cmp     dword ptr [rdi+834h], 0
0x1800191b8  lea     r14, [rdi+83Ch]
0x1800191bf  jz      short loc_1800191CB
0x1800191c1  mov     ecx, 800h
0x1800191c6  sub     ecx, [r14]
0x1800191c9  jmp     short loc_1800191CD
0x1800191cb  xor     ecx, ecx
0x1800191cd  cmp     cs:dword_18007E3F8, 0
0x1800191d4  jz      loc_180019368
0x1800191da  test    ebp, ebp
0x1800191dc  jnz     short loc_1800191E5
0x1800191de  lock inc cs:dword_18007E384
0x1800191e5  cmp     [rsp+98h+arg_20], 0
0x1800191ed  jz      loc_1800192E9
0x1800191f3  cmp     ebp, 10h
0x1800191f6  ja      short loc_180019204
0x1800191f8  lea     rax, byte_18007E390
0x1800191ff  jmp     loc_1800192C6
0x180019204  cmp     ebp, 20h ; ' '
0x180019207  ja      short loc_180019215
0x180019209  lea     rax, dword_18007E394
0x180019210  jmp     loc_1800192C6
0x180019215  cmp     ebp, 30h ; '0'
0x180019218  ja      short loc_180019226
0x18001921a  lea     rax, byte_18007E398
0x180019221  jmp     loc_1800192C6
0x180019226  cmp     ebp, 40h ; '@'
0x180019229  ja      short loc_180019237
0x18001922b  lea     rax, dword_18007E39C
0x180019232  jmp     loc_1800192C6
0x180019237  cmp     ebp, 80h
0x18001923d  ja      short loc_180019248
0x18001923f  lea     rax, byte_18007E3A0
0x180019246  jmp     short loc_1800192C6
0x180019248  cmp     ebp, 100h
0x18001924e  ja      short loc_180019259
0x180019250  lea     rax, dword_18007E3A4
0x180019257  jmp     short loc_1800192C6
0x180019259  cmp     ebp, 200h
0x18001925f  ja      short loc_18001926A
0x180019261  lea     rax, byte_18007E3A8
0x180019268  jmp     short loc_1800192C6
0x18001926a  cmp     ebp, 400h
0x180019270  ja      short loc_18001927B
0x180019272  lea     rax, dword_18007E3AC
0x180019279  jmp     short loc_1800192C6
0x18001927b  cmp     ebp, 800h
0x180019281  ja      short loc_18001928C
0x180019283  lea     rax, byte_18007E3B0
0x18001928a  jmp     short loc_1800192C6
0x18001928c  cmp     ebp, 1000h
0x180019292  ja      short loc_18001929D
0x180019294  lea     rax, dword_18007E3B4
0x18001929b  jmp     short loc_1800192C6
0x18001929d  cmp     ebp, 2000h
0x1800192a3  ja      short loc_1800192AE
0x1800192a5  lea     rax, byte_18007E3B8
0x1800192ac  jmp     short loc_1800192C6
0x1800192ae  cmp     ebp, 4000h
0x1800192b4  lea     rax, dword_18007E3BC
0x1800192bb  lea     rdx, byte_18007E3C0
0x1800192c2  cmova   rax, rdx
0x1800192c6  lock inc dword ptr [rax]
0x1800192c9  cmp     ebp, 0C0h
0x1800192cf  lea     rdx, byte_18007E388
0x1800192d6  lea     rax, dword_18007E38C
0x1800192dd  cmovbe  rax, rdx
0x1800192e1  lock add [rax], ebp
0x1800192e4  jmp     loc_180019376
0x1800192e9  lock inc cs:?sRespVecStats@@3UResponseVectorStatistics@@A; ResponseVectorStatistics sRespVecStats
0x1800192f0  cmp     ebp, ecx
0x1800192f2  ja      loc_1800193CA
0x1800192f8  mov     r8d, [rdi+838h]
0x1800192ff  mov     edx, [r14]
0x180019302  mov     rax, [rdi+820h]
0x180019309  mov     rbx, [rax+r8*8]
0x18001930d  mov     r8, rbp; Size
0x180019310  add     rbx, rdx
0x180019313  mov     rdx, r9; Src
0x180019316  mov     rcx, rbx; void *
0x180019319  call    memcpy_0
0x18001931e  mov     r8d, ebp; unsigned int
0x180019321  lea     rcx, [rdi+8]; this
0x180019325  mov     rdx, rbx; char *
0x180019328  call    ?Append@CResponseVector@@QEAAJPEADK@Z; CResponseVector::Append(char *,ulong)
0x18001932d  add     [r14], ebp
0x180019330  mov     edx, eax
0x180019332  cmp     [rsp+98h+var_60], 0
0x180019337  jz      loc_1800195AD
0x18001933d  movsxd  rax, r12d
0x180019340  lea     rdx, [rsp+98h+Buffer]
0x180019345  add     rdx, rax; char *
0x180019348  mov     [rsp+98h+var_78], 0; int
0x180019350  xor     r9d, r9d; int
0x180019353  mov     r8d, 2; unsigned int
0x180019359  mov     rcx, rdi; this
0x18001935c  call    ?Write@CResponseBuffer@@QEAAJPEADKHH@Z; CResponseBuffer::Write(char *,ulong,int,int)
0x180019361  mov     edx, eax
0x180019363  jmp     loc_1800195AD
0x180019368  cmp     [rsp+98h+arg_20], 0
0x180019370  jz      loc_1800192F0
0x180019376  cmp     ebp, 0C0h
0x18001937c  jbe     loc_1800192F0
0x180019382  mov     eax, [rdi+18h]
0x180019385  test    al, 1
0x180019387  jz      short loc_180019392
0x180019389  and     eax, 0FFFFFFFEh
0x18001938c  inc     dword ptr [rdi+14h]
0x18001938f  mov     [rdi+18h], eax
0x180019392  mov     r8d, ebp; unsigned int
0x180019395  lea     rcx, [rdi+8]; this
0x180019399  mov     rdx, r9; char *
0x18001939c  call    ?Append@CResponseVector@@QEAAJPEADK@Z; CResponseVector::Append(char *,ulong)
0x1800193a1  mov     edx, eax
0x1800193a3  mov     eax, [rdi+18h]
0x1800193a6  test    al, 1
0x1800193a8  jz      short loc_1800193B3
0x1800193aa  and     eax, 0FFFFFFFEh
0x1800193ad  inc     dword ptr [rdi+14h]
0x1800193b0  mov     [rdi+18h], eax
0x1800193b3  test    edx, edx
0x1800193b5  js      loc_180019332
0x1800193bb  mov     rcx, [rdi]; this
0x1800193be  call    ?AddTemplateToArray@CResponseBufferSet@@QEAAJXZ; CResponseBufferSet::AddTemplateToArray(void)
0x1800193c3  mov     edx, eax
0x1800193c5  jmp     loc_180019332
0x1800193ca  mov     r15d, ebp
0x1800193cd  sub     r15d, ecx
0x1800193d0  mov     ecx, [rdi+830h]
0x1800193d6  add     r15d, 7FFh
0x1800193dd  mov     eax, ecx
0x1800193df  sub     eax, [rdi+834h]
0x1800193e5  shr     r15d, 0Bh
0x1800193e9  cmp     r15d, eax
0x1800193ec  jbe     short loc_180019465
0x1800193ee  lea     ebx, [rcx+100h]
0x1800193f4  add     ebx, r15d
0x1800193f7  lea     eax, ds:0[rbx*8]
0x1800193fe  cmp     eax, ebx
0x180019400  jb      short loc_180019438
0x180019402  cmp     eax, 8
0x180019405  jb      short loc_180019438
0x180019407  xor     edx, edx; dwFlags
0x180019409  mov     r9d, eax; dwBytes
0x18001940c  cmp     ecx, 1
0x18001940f  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180019416  jnz     short loc_180019423
0x180019418  mov     r8d, r9d; dwBytes
0x18001941b  call    cs:__imp_HeapAlloc
0x180019421  jmp     short loc_180019430
0x180019423  mov     r8, [rdi+820h]; lpMem
0x18001942a  call    cs:__imp_HeapReAlloc
0x180019430  mov     rdx, rax
0x180019433  test    rax, rax
0x180019436  jnz     short loc_180019442
0x180019438  mov     edx, 8007000Eh
0x18001943d  jmp     loc_1800195AD
0x180019442  cmp     dword ptr [rdi+830h], 1
0x180019449  jnz     short loc_180019458
0x18001944b  mov     rax, [rdi+820h]
0x180019452  mov     rcx, [rax]
0x180019455  mov     [rdx], rcx
0x180019458  mov     [rdi+820h], rdx
0x18001945f  mov     [rdi+830h], ebx
0x180019465  xor     ebx, ebx
0x180019467  test    r15d, r15d
0x18001946a  jz      short loc_1800194A5
0x18001946c  nop     dword ptr [rax+00h]
0x180019470  mov     rcx, cs:?g_pachResponseBuffer@@3PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * g_pachResponseBuffer
0x180019477  test    rcx, rcx
0x18001947a  jz      short loc_180019438
0x18001947c  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180019482  test    rax, rax
0x180019485  jz      short loc_180019438
0x180019487  mov     edx, [rdi+834h]
0x18001948d  inc     ebx
0x18001948f  mov     rcx, [rdi+820h]
0x180019496  mov     [rcx+rdx*8], rax
0x18001949a  inc     dword ptr [rdi+834h]
0x1800194a0  cmp     ebx, r15d
0x1800194a3  jb      short loc_180019470
0x1800194a5  xor     edx, edx
0x1800194a7  test    ebp, ebp
0x1800194a9  jz      loc_180019332
0x1800194af  nop
0x1800194b0  cmp     dword ptr [r14], 800h
0x1800194b7  jnz     short loc_1800194D6
0x1800194b9  inc     dword ptr [rdi+838h]
0x1800194bf  mov     dword ptr [r14], 0
0x1800194c6  mov     eax, [rdi+18h]
0x1800194c9  test    al, 1
0x1800194cb  jz      short loc_1800194D6
0x1800194cd  and     eax, 0FFFFFFFEh
0x1800194d0  inc     dword ptr [rdi+14h]
0x1800194d3  mov     [rdi+18h], eax
0x1800194d6  mov     edx, [r14]
0x1800194d9  mov     ebx, 800h
0x1800194de  mov     ecx, [rdi+838h]
0x1800194e4  sub     ebx, edx
0x1800194e6  mov     rax, [rdi+820h]
0x1800194ed  cmp     ebp, ebx
0x1800194ef  cmovb   ebx, ebp
0x1800194f2  mov     r8d, ebx; Size
0x1800194f5  mov     r15, [rax+rcx*8]
0x1800194f9  add     r15, rdx
0x1800194fc  mov     r13d, ebx
0x1800194ff  mov     rdx, [rsp+98h+Src]; Src
0x180019504  mov     rcx, r15; void *
0x180019507  call    memcpy_0
0x18001950c  test    ebx, ebx
0x18001950e  jz      short loc_18001958C
0x180019510  test    byte ptr [rdi+18h], 1
0x180019514  mov     edx, [rdi+14h]
0x180019517  jz      short loc_180019543
0x180019519  mov     ecx, edx
0x18001951b  shl     rcx, 4
0x18001951f  cmp     edx, 80h
0x180019525  jnb     short loc_180019532
0x180019527  lea     rax, [rdi+20h]
0x18001952b  add     rax, rcx
0x18001952e  add     [rax], ebx
0x180019530  jmp     short loc_180019589
0x180019532  mov     rax, [rdi+8]
0x180019536  add     rax, 0FFFFFFFFFFFFF800h
0x18001953c  add     rax, rcx
0x18001953f  add     [rax], ebx
0x180019541  jmp     short loc_180019589
0x180019543  mov     eax, [rdi+10h]
0x180019546  sub     eax, 0FFFFFF80h
0x180019549  cmp     edx, eax
0x18001954b  jb      short loc_18001955C
0x18001954d  lea     rcx, [rdi+8]; this
  ... truncated ...
```
