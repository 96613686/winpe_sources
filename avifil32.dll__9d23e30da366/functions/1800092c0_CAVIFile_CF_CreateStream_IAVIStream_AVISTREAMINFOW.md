# CAVIFile::CF::CreateStream(IAVIStream * *,_AVISTREAMINFOW *)

- ea: `0x1800092c0`
- end: `0x1800095d0`
- name: `?CreateStream@CF@CAVIFile@@UEAAJPEAPEAUIAVIStream@@PEAU_AVISTREAMINFOW@@@Z`
- size: `784`
- prototype: `__int64 __fastcall(CAVIFile::CF *__hidden this, struct IAVIStream **, struct _AVISTREAMINFOW *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001008`
- `0x1800092c0`
- `0x18000c3b4`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000954e`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180009566`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000954e`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180009566`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800092ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800092ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009339`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000935a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009425`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800095b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009339`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000935a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009425`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800095b7`
- `USER32!SetRectEmpty` at `0x18000952e`
- `USER32!SetRectEmpty` at `0x18000952e`

## pseudocode

```c
__int64 __fastcall CAVIFile::CF::CreateStream(CAVIFile::CF *this, struct IAVIStream **a2, struct _AVISTREAMINFOW *a3)
{
  __int64 v3; // rdi
  __int64 v6; // r15
  int *v7; // r14
  int v8; // ebx
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  bool v12; // zf
  int v13; // eax
  int v14; // edx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax

  v3 = *((_QWORD *)this + 1);
  v6 = *(int *)(v3 + 104);
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 1264));
  v7 = (int *)(v3 + 136);
  if ( (*(int *)(v3 + 704) <= 0
     || (v8 = *v7, (signed int)(StringLenAsAnsi(a3->szName) + v8 + 96) <= *(_DWORD *)(v3 + 672)))
    && (*v7 += StringLenAsAnsi(a3->szName) + 96, (int)v6 < 64) )
  {
    if ( (*(_BYTE *)(v3 + 660) & 3) != 0 )
    {
      v10 = operator new(0x580u);
      v11 = v10;
      if ( v10 )
      {
        v10[1] = v10;
        *v10 = &CAVIStream::CUnknownImpl::`vftable';
        v10[3] = &CAVIStream::CS::`vftable';
        v10[5] = &CAVIStream::CStreamingImpl::`vftable';
        *((_DWORD *)v10 + 4) = 0;
        v10[4] = v10;
        v10[6] = v10;
        v10[7] = v10;
        v10[36] = 0;
        v10[37] = 0;
        v10[167] = 0;
        *((_DWORD *)v10 + 336) = 0;
        v10[169] = 0;
        *((_DWORD *)v10 + 340) = 0;
        v10[171] = 0;
        *((_DWORD *)v10 + 344) = 0;
        v10[175] = 0;
        *((_DWORD *)v10 + 76) = 0;
        v10[173] = 0;
        *((_DWORD *)v10 + 348) = 0;
      }
      else
      {
        v11 = 0;
      }
      *(_QWORD *)(v3 + 8 * v6 + 736) = v11;
      if ( v11 )
      {
        *((_DWORD *)v11 + 70) = v6;
        v11[34] = v3;
        *((_OWORD *)v11 + 4) = *(_OWORD *)&a3->fccType;
        *((_OWORD *)v11 + 5) = *(_OWORD *)&a3->wPriority;
        *((_OWORD *)v11 + 6) = *(_OWORD *)&a3->dwLength;
        *((_OWORD *)v11 + 7) = *(_OWORD *)&a3->dwSampleSize;
        *((_OWORD *)v11 + 8) = *(_OWORD *)&a3->rcFrame.bottom;
        *((_OWORD *)v11 + 9) = *(_OWORD *)&a3->szName[2];
        *((_OWORD *)v11 + 10) = *(_OWORD *)&a3->szName[10];
        *((_OWORD *)v11 + 11) = *(_OWORD *)&a3->szName[18];
        *((_OWORD *)v11 + 12) = *(_OWORD *)&a3->szName[26];
        *((_OWORD *)v11 + 13) = *(_OWORD *)&a3->szName[34];
        *((_OWORD *)v11 + 14) = *(_OWORD *)&a3->szName[42];
        *((_OWORD *)v11 + 15) = *(_OWORD *)&a3->szName[50];
        *(_OWORD *)((char *)v11 + 252) = *(_OWORD *)&a3->szName[56];
        *((_DWORD *)v11 + 24) = 0;
        *((_DWORD *)v11 + 26) = 0;
        v11[37] = *(_QWORD *)(v3 + 664);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v11[4] + 56LL) + 8LL))(*(_QWORD *)(v11[4] + 56LL));
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 72LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 1) + 72LL));
        v12 = *((_DWORD *)v11 + 16) == 1935963489;
        v11[167] = 0;
        *((_DWORD *)v11 + 336) = 0;
        if ( v12 )
          SetRectEmpty((LPRECT)((char *)v11 + 116));
        ++*(_DWORD *)(v3 + 104);
        if ( !*((_DWORD *)v11 + 70) )
        {
          v13 = MulDiv(1000000, *((_DWORD *)v11 + 21), *((_DWORD *)v11 + 22));
          v14 = 1000;
          if ( v13 >= 1000 )
            v14 = MulDiv(1000000, *((_DWORD *)v11 + 21), *((_DWORD *)v11 + 22));
          *(_DWORD *)(v11[34] + 80LL) = v14;
        }
        v15 = *(_DWORD *)(v3 + 112);
        if ( v15 <= *((_DWORD *)v11 + 31) )
          v15 = *((_DWORD *)v11 + 31);
        *(_DWORD *)(v3 + 112) = v15;
        v16 = *(_DWORD *)(v3 + 116);
        if ( v16 <= *((_DWORD *)v11 + 32) )
          v16 = *((_DWORD *)v11 + 32);
        *(_DWORD *)(v3 + 116) = v16;
        v17 = *(_DWORD *)(v3 + 100);
        if ( v17 <= *((_DWORD *)v11 + 25) )
          v17 = *((_DWORD *)v11 + 25);
        *(_DWORD *)(v3 + 100) = v17;
        *a2 = (struct IAVIStream *)(v11 + 3);
        if ( v3 != -1264 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 1264));
        return 0;
      }
      else
      {
        if ( v3 != -1264 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 1264));
        return 2147762279LL;
      }
    }
    else
    {
      if ( v3 != -1264 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 1264));
      return 2147762290LL;
    }
  }
  else
  {
    if ( v3 != -1264 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 1264));
    return 2147762277LL;
  }
}

```

## disassembly

```asm
0x1800092c0  mov     [rsp+arg_8], rdx
0x1800092c5  push    rbx
0x1800092c6  push    rbp
0x1800092c7  push    rsi
0x1800092c8  push    rdi
0x1800092c9  push    r12
0x1800092cb  push    r13
0x1800092cd  push    r14
0x1800092cf  push    r15
0x1800092d1  sub     rsp, 28h
0x1800092d5  mov     rdi, [rcx+8]
0x1800092d9  mov     r13, rcx
0x1800092dc  mov     rbp, r8
0x1800092df  movsxd  r15, dword ptr [rdi+68h]
0x1800092e3  lea     rsi, [rdi+4F0h]
0x1800092ea  mov     rcx, rsi; lpCriticalSection
0x1800092ed  call    cs:__imp_EnterCriticalSection
0x1800092f3  cmp     dword ptr [rdi+2C0h], 0
0x1800092fa  lea     r14, [rdi+88h]
0x180009301  jle     short loc_18000931C
0x180009303  mov     ebx, [r14]
0x180009306  lea     rcx, [rbp+4Ch]; lpWideCharStr
0x18000930a  call    StringLenAsAnsi
0x18000930f  lea     edx, [rbx+60h]
0x180009312  add     edx, eax
0x180009314  cmp     edx, [rdi+2A0h]
0x18000931a  jg      short loc_180009331
0x18000931c  lea     rcx, [rbp+4Ch]; lpWideCharStr
0x180009320  call    StringLenAsAnsi
0x180009325  add     eax, 60h ; '`'
0x180009328  add     [r14], eax
0x18000932b  cmp     r15d, 40h ; '@'
0x18000932f  jl      short loc_180009349
0x180009331  test    rsi, rsi
0x180009334  jz      short loc_18000933F
0x180009336  mov     rcx, rsi; lpCriticalSection
0x180009339  call    cs:__imp_LeaveCriticalSection
0x18000933f  mov     eax, 80044065h
0x180009344  jmp     loc_1800095BF
0x180009349  test    byte ptr [rdi+294h], 3
0x180009350  jnz     short loc_18000936A
0x180009352  test    rsi, rsi
0x180009355  jz      short loc_180009360
0x180009357  mov     rcx, rsi; lpCriticalSection
0x18000935a  call    cs:__imp_LeaveCriticalSection
0x180009360  mov     eax, 80044072h
0x180009365  jmp     loc_1800095BF
0x18000936a  mov     ecx, 580h; Size
0x18000936f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009374  xor     r14d, r14d
0x180009377  mov     rbx, rax
0x18000937a  test    rax, rax
0x18000937d  jz      loc_18000940D
0x180009383  lea     rax, ??_7CUnknownImpl@CAVIStream@@6B@; const CAVIStream::CUnknownImpl::`vftable'
0x18000938a  mov     [rbx+8], rbx
0x18000938e  mov     [rbx], rax
0x180009391  lea     rax, ??_7CS@CAVIStream@@6B@; const CAVIStream::CS::`vftable'
0x180009398  mov     [rbx+18h], rax
0x18000939c  lea     rax, ??_7CStreamingImpl@CAVIStream@@6B@; const CAVIStream::CStreamingImpl::`vftable'
0x1800093a3  mov     [rbx+28h], rax
0x1800093a7  mov     [rbx+10h], r14d
0x1800093ab  mov     [rbx+20h], rbx
0x1800093af  mov     [rbx+30h], rbx
0x1800093b3  mov     [rbx+38h], rbx
0x1800093b7  mov     [rbx+120h], r14
0x1800093be  mov     [rbx+128h], r14
0x1800093c5  mov     [rbx+538h], r14
0x1800093cc  mov     [rbx+540h], r14d
0x1800093d3  mov     [rbx+548h], r14
0x1800093da  mov     [rbx+550h], r14d
0x1800093e1  mov     [rbx+558h], r14
0x1800093e8  mov     [rbx+560h], r14d
0x1800093ef  mov     [rbx+578h], r14
0x1800093f6  mov     [rbx+130h], r14d
0x1800093fd  mov     [rbx+568h], r14
0x180009404  mov     [rbx+570h], r14d
0x18000940b  jmp     short loc_180009410
0x18000940d  mov     rbx, r14
0x180009410  mov     [rdi+r15*8+2E0h], rbx
0x180009418  test    rbx, rbx
0x18000941b  jnz     short loc_180009435
0x18000941d  test    rsi, rsi
0x180009420  jz      short loc_18000942B
0x180009422  mov     rcx, rsi; lpCriticalSection
0x180009425  call    cs:__imp_LeaveCriticalSection
0x18000942b  mov     eax, 80044067h
0x180009430  jmp     loc_1800095BF
0x180009435  mov     [rbx+118h], r15d
0x18000943c  mov     [rbx+110h], rdi
0x180009443  movups  xmm0, xmmword ptr [rbp+0]
0x180009447  movups  xmmword ptr [rbx+40h], xmm0
0x18000944b  movups  xmm1, xmmword ptr [rbp+10h]
0x18000944f  movups  xmmword ptr [rbx+50h], xmm1
0x180009453  movups  xmm0, xmmword ptr [rbp+20h]
0x180009457  movups  xmmword ptr [rbx+60h], xmm0
0x18000945b  movups  xmm1, xmmword ptr [rbp+30h]
0x18000945f  movups  xmmword ptr [rbx+70h], xmm1
0x180009463  movups  xmm0, xmmword ptr [rbp+40h]
0x180009467  movups  xmmword ptr [rbx+80h], xmm0
0x18000946e  movups  xmm1, xmmword ptr [rbp+50h]
0x180009472  movups  xmmword ptr [rbx+90h], xmm1
0x180009479  movups  xmm0, xmmword ptr [rbp+60h]
0x18000947d  movups  xmmword ptr [rbx+0A0h], xmm0
0x180009484  movups  xmm1, xmmword ptr [rbp+70h]
0x180009488  movups  xmmword ptr [rbx+0B0h], xmm1
0x18000948f  movups  xmm0, xmmword ptr [rbp+80h]
0x180009496  movups  xmmword ptr [rbx+0C0h], xmm0
0x18000949d  movups  xmm1, xmmword ptr [rbp+90h]
0x1800094a4  movups  xmmword ptr [rbx+0D0h], xmm1
0x1800094ab  movups  xmm0, xmmword ptr [rbp+0A0h]
0x1800094b2  movups  xmmword ptr [rbx+0E0h], xmm0
0x1800094b9  movups  xmm1, xmmword ptr [rbp+0B0h]
0x1800094c0  movups  xmmword ptr [rbx+0F0h], xmm1
0x1800094c7  movups  xmm0, xmmword ptr [rbp+0BCh]
0x1800094ce  movups  xmmword ptr [rbx+0FCh], xmm0
0x1800094d5  mov     [rbx+60h], r14d
0x1800094d9  mov     [rbx+68h], r14d
0x1800094dd  mov     rax, [rdi+298h]
0x1800094e4  mov     [rbx+128h], rax
0x1800094eb  mov     rax, [rbx+20h]
0x1800094ef  mov     rcx, [rax+38h]
0x1800094f3  mov     rax, [rcx]
0x1800094f6  mov     rax, [rax+8]
0x1800094fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094ff  mov     rax, [r13+8]
0x180009503  mov     rcx, [rax+48h]
0x180009507  mov     rax, [rcx]
0x18000950a  mov     rax, [rax+8]
0x18000950e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009513  cmp     dword ptr [rbx+40h], 73647561h
0x18000951a  mov     [rbx+538h], r14
0x180009521  mov     [rbx+540h], r14d
0x180009528  jnz     short loc_180009534
0x18000952a  lea     rcx, [rbx+74h]; lprc
0x18000952e  call    cs:__imp_SetRectEmpty
0x180009534  inc     dword ptr [rdi+68h]
0x180009537  cmp     [rbx+118h], r14d
0x18000953e  jnz     short loc_180009578
0x180009540  mov     r8d, [rbx+58h]; nDenominator
0x180009544  mov     ebp, 0F4240h
0x180009549  mov     edx, [rbx+54h]; nNumerator
0x18000954c  mov     ecx, ebp; nNumber
0x18000954e  call    cs:__imp_MulDiv
0x180009554  mov     edx, 3E8h
0x180009559  cmp     eax, edx
0x18000955b  jl      short loc_18000956E
0x18000955d  mov     r8d, [rbx+58h]; nDenominator
0x180009561  mov     ecx, ebp; nNumber
0x180009563  mov     edx, [rbx+54h]; nNumerator
0x180009566  call    cs:__imp_MulDiv
0x18000956c  mov     edx, eax
0x18000956e  mov     rcx, [rbx+110h]
0x180009575  mov     [rcx+50h], edx
0x180009578  mov     eax, [rdi+70h]
0x18000957b  cmp     eax, [rbx+7Ch]
0x18000957e  cmovbe  eax, [rbx+7Ch]
0x180009582  mov     [rdi+70h], eax
0x180009585  mov     ecx, [rbx+80h]
0x18000958b  mov     eax, [rdi+74h]
0x18000958e  cmp     eax, ecx
0x180009590  cmovbe  eax, ecx
0x180009593  mov     rcx, [rsp+68h+arg_8]
0x180009598  mov     [rdi+74h], eax
0x18000959b  mov     eax, [rdi+64h]
0x18000959e  cmp     eax, [rbx+64h]
0x1800095a1  cmovbe  eax, [rbx+64h]
0x1800095a5  mov     [rdi+64h], eax
0x1800095a8  lea     rax, [rbx+18h]
0x1800095ac  mov     [rcx], rax
0x1800095af  test    rsi, rsi
0x1800095b2  jz      short loc_1800095BD
0x1800095b4  mov     rcx, rsi; lpCriticalSection
0x1800095b7  call    cs:__imp_LeaveCriticalSection
0x1800095bd  xor     eax, eax
0x1800095bf  add     rsp, 28h
0x1800095c3  pop     r15
0x1800095c5  pop     r14
0x1800095c7  pop     r13
0x1800095c9  pop     r12
0x1800095cb  pop     rdi
0x1800095cc  pop     rsi
0x1800095cd  pop     rbp
0x1800095ce  pop     rbx
0x1800095cf  retn
```
