# OLog::AddLine(Mso::Logging::Severity,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)

- ea: `0x180020ef0`
- end: `0x180021244`
- name: `?AddLine@OLog@@QEAAXW4Severity@Logging@Mso@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z`
- size: `852`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x180021610`
- `0x180021c30`

## callees

- `0x180001bac`
- `0x180004044`
- `0x1800045ec`
- `0x1800046d8`
- `0x18000afcc`
- `0x180020c88`
- `0x180020ef0`
- `0x180021610`
- `0x180022194`
- `0x18002265c`
- `0x180022b34`
- `0x1800266e0`
- `0x18002b780`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180020f34`
- `KERNEL32!GetCurrentThreadId` at `0x180020f51`
- `KERNEL32!GetCurrentThreadId` at `0x18002104d`
- `KERNEL32!GetCurrentThreadId` at `0x180020f34`
- `KERNEL32!GetCurrentThreadId` at `0x180020f51`
- `KERNEL32!GetCurrentThreadId` at `0x18002104d`
- `KERNEL32!EnterCriticalSection` at `0x180020f45`
- `KERNEL32!EnterCriticalSection` at `0x180020f45`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800211fd`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800211fd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180021207`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180021207`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OLog::AddLine(__int64 a1, unsigned __int8 a2, const wchar_t **a3)
{
  __int64 v6; // r8
  unsigned int v7; // edx
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  const wchar_t *v10; // rax
  int v11; // eax
  int v12; // edx
  __int64 v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // r14
  void **v16; // r13
  char *v17; // rdi
  unsigned __int64 v18; // r12
  __int64 v19; // rcx
  __int64 v20; // r15
  void *v21; // rax
  char *v22; // rcx
  __int64 v24; // [rsp+30h] [rbp-69h] BYREF
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+38h] [rbp-61h] BYREF
  char v26; // [rsp+40h] [rbp-59h]
  char v27[8]; // [rsp+48h] [rbp-51h] BYREF
  void *Src[2]; // [rsp+50h] [rbp-49h] BYREF
  __m128i si128; // [rsp+60h] [rbp-39h]
  _OWORD v30[2]; // [rsp+70h] [rbp-29h] BYREF
  _QWORD v31[2]; // [rsp+90h] [rbp-9h] BYREF
  __m128i v32; // [rsp+A0h] [rbp+7h]

  v25 = &CriticalSection;
  v26 = 0;
  if ( dword_180065BB4 != GetCurrentThreadId() )
  {
    EnterCriticalSection(&CriticalSection);
    ++dword_180065BB0;
    dword_180065BB4 = GetCurrentThreadId();
    v26 = 1;
  }
  v7 = 10;
  if ( (byte_1800655C2 & 1) != 0 )
  {
    v30[0] = MSOLogging;
    switch ( a2 )
    {
      case 6u:
      case 0xAu:
        BYTE4(v30[0]) = 2;
        break;
      case 0xFu:
      case 0x32u:
        BYTE4(v30[0]) = 4;
        break;
      case 0x64u:
      case 0xC8u:
        BYTE4(v30[0]) = 5;
        break;
      default:
        goto LABEL_22;
    }
    v8 = (const wchar_t *)a3;
    if ( (unsigned __int64)a3[3] > 7 )
      v8 = *a3;
    if ( v8 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
      v7 = 2 * v9 + 2;
    }
    v10 = L"NULL";
    if ( v8 )
      v10 = v8;
    v32.m128i_i64[0] = (__int64)v10;
    v32.m128i_i64[1] = v7;
    McGenEventWrite_EventWriteTransfer(guidProviderOfficeUtilStat_Context, v30, v6, 2, v31);
  }
LABEL_22:
  *(_OWORD *)Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src[0]) = 0;
  v27[0] = a2;
  if ( *(_BYTE *)(a1 + 130) || *(_BYTE *)a1 >= 0x64u )
  {
    LODWORD(v24) = GetCurrentThreadId();
    v11 = OSystem::CurrentLongTime(v30);
    v13 = OString::Format<std::wstring,unsigned long,std::wstring>(
            (unsigned int)v31,
            v12,
            v11,
            (unsigned int)&v24,
            (__int64)a3);
    if ( Src != (void **)v13 )
    {
      *(_OWORD *)Src = *(_OWORD *)v13;
      si128 = *(__m128i *)(v13 + 16);
      *(_QWORD *)(v13 + 16) = 0;
      *(_QWORD *)(v13 + 24) = 7;
      *(_WORD *)v13 = 0;
    }
    std::wstring::_Tidy_deallocate(v31);
    v31[0] = 19937;
    v32 = _mm_load_si128((const __m128i *)&_xmm);
    std::wstring::_Tidy_deallocate(v30);
  }
  else
  {
    std::wstring::operator=(Src);
    a2 = v27[0];
  }
  if ( a2 < *(_BYTE *)(a1 + 1) )
    *(_BYTE *)(a1 + 1) = a2;
  v14 = *(_QWORD *)(a1 + 48);
  if ( v14 == *(_QWORD *)(a1 + 56) )
  {
    std::vector<OLog::OLogLine>::_Emplace_reallocate<OLog::OLogLine const &>(a1 + 40, v14, v27);
    v18 = si128.m128i_u64[1];
    v17 = (char *)Src[0];
  }
  else
  {
    *(_BYTE *)v14 = a2;
    v15 = (_QWORD *)(v14 + 8);
    *(_QWORD *)&v30[0] = v14 + 8;
    *(_OWORD *)(v14 + 8) = 0;
    *(_QWORD *)(v14 + 24) = 0;
    *(_QWORD *)(v14 + 32) = 0;
    v16 = Src;
    v17 = (char *)Src[0];
    v18 = si128.m128i_u64[1];
    if ( si128.m128i_i64[1] > 7uLL )
      v16 = (void **)Src[0];
    v19 = 0x7FFFFFFFFFFFFFFELL;
    v20 = si128.m128i_i64[0];
    if ( si128.m128i_i64[0] > 0x7FFFFFFFFFFFFFFEuLL )
      std::_Xlen_string();
    if ( si128.m128i_i64[0] > 7uLL )
    {
      if ( (si128.m128i_i64[0] | 7uLL) <= 0x7FFFFFFFFFFFFFFELL )
      {
        v19 = si128.m128i_i64[0] | 7;
        if ( (si128.m128i_i64[0] | 7uLL) < 0xA )
          v19 = 10;
      }
      v24 = v19;
      v21 = (void *)std::wstring::_Allocate_for_capacity<0>(v15, &v24);
      *v15 = v21;
      v15[2] = v20;
      v15[3] = v24;
      memmove(v21, v16, 2 * v20 + 2);
    }
    else
    {
      *(_QWORD *)(v14 + 24) = si128.m128i_i64[0];
      *(_QWORD *)(v14 + 32) = 7;
      *(_OWORD *)v15 = *(_OWORD *)v16;
    }
    *(_QWORD *)(a1 + 48) += 40LL;
  }
  if ( *(_BYTE *)(a1 + 129) && *(_QWORD *)(a1 + 24) )
    OLog::Flush((_QWORD *)a1, *(_BYTE *)a1);
  if ( v18 > 7 )
  {
    v22 = v17;
    if ( 2 * v18 + 2 >= 0x1000 )
    {
      v17 = (char *)*((_QWORD *)v17 - 1);
      if ( (unsigned __int64)(v22 - v17 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v17);
  }
  return AcquireExclusive<OLock>::~AcquireExclusive<OLock>(&v25);
}

```

## disassembly

```asm
0x180020ef0  mov     [rsp-8+arg_18], rbx
0x180020ef5  push    rbp
0x180020ef6  push    rsi
0x180020ef7  push    rdi
0x180020ef8  push    r12
0x180020efa  push    r13
0x180020efc  push    r14
0x180020efe  push    r15
0x180020f00  lea     rbp, [rsp-27h]
0x180020f05  sub     rsp, 0C0h
0x180020f0c  mov     rax, cs:__security_cookie
0x180020f13  xor     rax, rsp
0x180020f16  mov     [rbp+57h+var_40], rax
0x180020f1a  mov     rsi, r8
0x180020f1d  mov     edi, edx
0x180020f1f  mov     rbx, rcx
0x180020f22  lea     r14, CriticalSection
0x180020f29  mov     [rbp+57h+var_B8], r14
0x180020f2d  xor     r15d, r15d
0x180020f30  mov     [rbp+57h+var_B0], r15b
0x180020f34  call    cs:__imp_GetCurrentThreadId
0x180020f3a  cmp     cs:dword_180065BB4, eax
0x180020f40  jz      short loc_180020F61
0x180020f42  mov     rcx, r14; lpCriticalSection
0x180020f45  call    cs:__imp_EnterCriticalSection
0x180020f4b  inc     cs:dword_180065BB0
0x180020f51  call    cs:__imp_GetCurrentThreadId
0x180020f57  mov     cs:dword_180065BB4, eax
0x180020f5d  mov     [rbp+57h+var_B0], 1
0x180020f61  mov     edx, 0Ah
0x180020f66  test    cs:byte_1800655C2, 1
0x180020f6d  jz      loc_180021010
0x180020f73  movups  xmm0, cs:MSOLogging
0x180020f7a  movdqu  [rbp+57h+var_80], xmm0
0x180020f7f  movzx   ecx, dil
0x180020f83  sub     ecx, 6
0x180020f86  jz      short loc_180020FAD
0x180020f88  sub     ecx, 4
0x180020f8b  jz      short loc_180020FAD
0x180020f8d  sub     ecx, 5
0x180020f90  jz      short loc_180020FA7
0x180020f92  sub     ecx, 23h ; '#'
0x180020f95  jz      short loc_180020FA7
0x180020f97  sub     ecx, 32h ; '2'
0x180020f9a  jz      short loc_180020FA1
0x180020f9c  cmp     ecx, 64h ; 'd'
0x180020f9f  jnz     short loc_180021010
0x180020fa1  mov     byte ptr [rbp+57h+var_80+4], 5
0x180020fa5  jmp     short loc_180020FB1
0x180020fa7  mov     byte ptr [rbp+57h+var_80+4], 4
0x180020fab  jmp     short loc_180020FB1
0x180020fad  mov     byte ptr [rbp+57h+var_80+4], 2
0x180020fb1  mov     rcx, rsi
0x180020fb4  cmp     qword ptr [rsi+18h], 7
0x180020fb9  jbe     short loc_180020FBE
0x180020fbb  mov     rcx, [rsi]
0x180020fbe  test    rcx, rcx
0x180020fc1  jz      short loc_180020FD8
0x180020fc3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020fc7  inc     rax
0x180020fca  cmp     [rcx+rax*2], r15w
0x180020fcf  jnz     short loc_180020FC7
0x180020fd1  lea     edx, ds:2[rax*2]
0x180020fd8  lea     rax, aNull_0; "NULL"
0x180020fdf  test    rcx, rcx
0x180020fe2  cmovnz  rax, rcx
0x180020fe6  mov     qword ptr [rbp+57h+var_50], rax
0x180020fea  mov     dword ptr [rbp+57h+var_50+8], edx
0x180020fed  mov     dword ptr [rbp+57h+var_50+0Ch], r15d
0x180020ff1  lea     rax, [rbp+57h+var_60]
0x180020ff5  mov     [rsp+0F0h+Reserved], rax
0x180020ffa  mov     r9d, 2
0x180021000  lea     rdx, [rbp+57h+var_80]
0x180021004  lea     rcx, guidProviderOfficeUtilStat_Context
0x18002100b  call    McGenEventWrite_EventWriteTransfer
0x180021010  xorps   xmm0, xmm0
0x180021013  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180021017  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002101f  movdqu  [rbp+57h+var_90], xmm1
0x180021024  mov     word ptr [rbp+57h+Src], r15w
0x180021029  mov     [rbp+57h+var_A8], dil
0x18002102d  cmp     [rbx+82h], r15b
0x180021034  jnz     short loc_18002104D
0x180021036  cmp     byte ptr [rbx], 64h ; 'd'
0x180021039  jnb     short loc_18002104D
0x18002103b  mov     rdx, rsi
0x18002103e  lea     rcx, [rbp+57h+Src]; void *
0x180021042  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180021047  mov     dil, [rbp+57h+var_A8]
0x18002104b  jmp     short loc_1800210C4
0x18002104d  call    cs:__imp_GetCurrentThreadId
0x180021053  mov     dword ptr [rbp+57h+var_C0], eax
0x180021056  lea     rcx, [rbp+57h+var_80]
0x18002105a  call    ?CurrentLongTime@OSystem@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; OSystem::CurrentLongTime(void)
0x18002105f  nop
0x180021060  mov     [rsp+0F0h+Reserved], rsi
0x180021065  lea     r9, [rbp+57h+var_C0]
0x180021069  mov     r8, rax
0x18002106c  lea     rcx, [rbp+57h+var_60]
0x180021070  call    ??$Format@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@@OString@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WAEBV12@AEBK1@Z; OString::Format<std::wstring,ulong,std::wstring>(wchar_t const *,std::wstring const &,ulong const &,std::wstring const &)
0x180021075  lea     rcx, [rbp+57h+Src]
0x180021079  cmp     rcx, rax
0x18002107c  jz      short loc_18002109D
0x18002107e  movups  xmm0, xmmword ptr [rax]
0x180021081  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180021085  movups  xmm1, xmmword ptr [rax+10h]
0x180021089  movups  [rbp+57h+var_90], xmm1
0x18002108d  mov     [rax+10h], r15
0x180021091  mov     qword ptr [rax+18h], 7
0x180021099  mov     [rax], r15w
0x18002109d  lea     rcx, [rbp+57h+var_60]
0x1800210a1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800210a6  mov     [rbp+57h+var_60], 4DE1h
0x1800210ae  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800210b6  movdqu  [rbp+57h+var_50], xmm0
0x1800210bb  lea     rcx, [rbp+57h+var_80]
0x1800210bf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800210c4  cmp     dil, [rbx+1]
0x1800210c8  jnb     short loc_1800210CE
0x1800210ca  mov     [rbx+1], dil
0x1800210ce  mov     rdx, [rbx+30h]
0x1800210d2  cmp     rdx, [rbx+38h]
0x1800210d6  jz      loc_180021195
0x1800210dc  mov     [rdx], dil
0x1800210df  lea     r14, [rdx+8]
0x1800210e3  mov     qword ptr [rbp+57h+var_80], r14
0x1800210e7  xorps   xmm0, xmm0
0x1800210ea  movups  xmmword ptr [r14], xmm0
0x1800210ee  mov     [r14+10h], r15
0x1800210f2  mov     [r14+18h], r15
0x1800210f6  lea     r13, [rbp+57h+Src]
0x1800210fa  mov     rdi, [rbp+57h+Src]
0x1800210fe  mov     r12, qword ptr [rbp+57h+var_90+8]
0x180021102  mov     edx, 7
0x180021107  cmp     r12, rdx
0x18002110a  cmova   r13, rdi
0x18002110e  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180021118  mov     r15, qword ptr [rbp+57h+var_90]
0x18002111c  cmp     r15, rcx
0x18002111f  ja      loc_18002123E
0x180021125  cmp     r15, rdx
0x180021128  ja      short loc_18002113E
0x18002112a  mov     [r14+10h], r15
0x18002112e  mov     [r14+18h], rdx
0x180021132  movups  xmm0, xmmword ptr [r13+0]
0x180021137  movdqu  xmmword ptr [r14], xmm0
0x18002113c  jmp     short loc_18002118B
0x18002113e  mov     rax, r15
0x180021141  or      rax, rdx
0x180021144  cmp     rax, rcx
0x180021147  ja      short loc_180021158
0x180021149  mov     rcx, rax
0x18002114c  mov     edx, 0Ah
0x180021151  cmp     rax, rdx
0x180021154  cmovb   rcx, rdx
0x180021158  mov     [rbp+57h+var_C0], rcx
0x18002115c  lea     rdx, [rbp+57h+var_C0]
0x180021160  mov     rcx, r14
0x180021163  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x180021168  mov     [r14], rax
0x18002116b  mov     [r14+10h], r15
0x18002116f  mov     rcx, [rbp+57h+var_C0]
0x180021173  mov     [r14+18h], rcx
0x180021177  lea     r8, ds:2[r15*2]; Size
0x18002117f  mov     rdx, r13; Src
0x180021182  mov     rcx, rax; void *
0x180021185  call    memmove
0x18002118a  nop
0x18002118b  add     qword ptr [rbx+30h], 28h ; '('
0x180021190  xor     r15d, r15d
0x180021193  jmp     short loc_1800211AA
0x180021195  lea     r8, [rbp+57h+var_A8]
0x180021199  lea     rcx, [rbx+28h]
0x18002119d  call    ??$_Emplace_reallocate@AEBUOLogLine@OLog@@@?$vector@UOLogLine@OLog@@V?$allocator@UOLogLine@OLog@@@std@@@std@@AEAAPEAUOLogLine@OLog@@QEAU23@AEBU23@@Z; std::vector<OLog::OLogLine>::_Emplace_reallocate<OLog::OLogLine const &>(OLog::OLogLine * const,OLog::OLogLine const &)
0x1800211a2  mov     r12, qword ptr [rbp+57h+var_90+8]
0x1800211a6  mov     rdi, [rbp+57h+Src]
0x1800211aa  cmp     [rbx+81h], r15b
0x1800211b1  jz      short loc_1800211C4
0x1800211b3  cmp     [rbx+18h], r15
0x1800211b7  jz      short loc_1800211C4
0x1800211b9  mov     dl, [rbx]
0x1800211bb  mov     rcx, rbx
0x1800211be  call    ?Flush@OLog@@QEAAXW4MinimumSeverity@Logging@Mso@@@Z; OLog::Flush(Mso::Logging::MinimumSeverity)
0x1800211c3  nop
0x1800211c4  cmp     r12, 7
0x1800211c8  jbe     short loc_18002120E
0x1800211ca  mov     rcx, rdi
0x1800211cd  lea     rax, ds:2[r12*2]
0x1800211d5  cmp     rax, 1000h
0x1800211db  jb      short loc_180021204
0x1800211dd  mov     rdi, [rdi-8]
0x1800211e1  sub     rcx, rdi
0x1800211e4  lea     rax, [rcx-8]
0x1800211e8  cmp     rax, 1Fh
0x1800211ec  jbe     short loc_180021204
0x1800211ee  mov     [rsp+0F0h+Reserved], r15; Reserved
0x1800211f3  xor     r9d, r9d; LineNo
0x1800211f6  xor     r8d, r8d; FileName
0x1800211f9  xor     edx, edx; FunctionName
0x1800211fb  xor     ecx, ecx; Expression
0x1800211fd  call    cs:__imp__invoke_watson
0x180021204  mov     rcx, rdi; Block
0x180021207  call    cs:__imp_free
0x18002120d  nop
0x18002120e  lea     rcx, [rbp+57h+var_B8]
0x180021212  call    ??1?$AcquireExclusive@VOLock@@@@QEAA@XZ; AcquireExclusive<OLock>::~AcquireExclusive<OLock>(void)
0x180021217  mov     rcx, [rbp+57h+var_40]
0x18002121b  xor     rcx, rsp; StackCookie
0x18002121e  call    __security_check_cookie
0x180021223  mov     rbx, [rsp+0F0h+arg_18]
0x18002122b  add     rsp, 0C0h
0x180021232  pop     r15
0x180021234  pop     r14
0x180021236  pop     r13
0x180021238  pop     r12
0x18002123a  pop     rdi
0x18002123b  pop     rsi
0x18002123c  pop     rbp
0x18002123d  retn
0x18002123e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
