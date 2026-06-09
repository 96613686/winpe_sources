# File::WriteOneEventToBuffer(BinXmlReader &,AbstractPublishedEventRecord *,_FILETIME,utl::unique_lock<utl::shared_mutex> &)

- ea: `0x18003409c`
- end: `0x18003451d`
- name: `?WriteOneEventToBuffer@File@@AEAAKAEAVBinXmlReader@@PEAVAbstractPublishedEventRecord@@U_FILETIME@@AEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z`
- size: `1153`
- prototype: `__int64 __usercall@<rax>(File *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x180034524`

## callees

- `0x180007180`
- `0x18000a0d0`
- `0x1800223c8`
- `0x180023548`
- `0x180031084`
- `0x180032bb8`
- `0x180033034`
- `0x18003409c`
- `0x1800355b8`
- `0x180038fb4`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180034420`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180034420`

## pseudocode

```c
__int64 __fastcall File::WriteOneEventToBuffer(
        LPCWSTR *this,
        struct BinXmlReader *a2,
        void (__fastcall ***a3)(_QWORD, LPCWSTR, __int64),
        __int64 a4,
        __int64 a5)
{
  __int64 result; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // rcx
  unsigned __int64 v12; // rdx
  char v13; // r8
  __int64 v14; // rsi
  _OWORD *v15; // rbx
  const WCHAR *v16; // rdx
  _OWORD *v17; // rcx
  __int64 v18; // rdx
  _OWORD *v19; // rax
  __int128 v20; // xmm1
  _OWORD *v21; // rax
  LPCWSTR v22; // r14
  void (__fastcall **v23)(_QWORD, LPCWSTR, __int64); // rax
  LPCWSTR v24; // r9
  unsigned int v25; // r15d
  LPCWSTR v26; // rdx
  __int64 v27; // rax
  LPCWSTR v28; // rcx
  WCHAR *v29; // rax
  __int128 v30; // xmm1
  WCHAR *v31; // rax
  unsigned __int64 UnbiasedTime; // [rsp+30h] [rbp-38h] BYREF
  __int128 pExceptionObject; // [rsp+38h] [rbp-30h] BYREF
  __int64 v34; // [rsp+48h] [rbp-20h]
  int v35; // [rsp+50h] [rbp-18h]
  int v36; // [rsp+54h] [rbp-14h]
  int v37; // [rsp+58h] [rbp-10h]

  result = File::EnsureFileIsCreated(this);
  if ( !(_DWORD)result )
  {
    *((_DWORD *)this + 204) = 0;
    if ( *((_BYTE *)this + 829) && *((_BYTE *)this + 830) )
    {
      if ( !*((_BYTE *)this + 828) )
      {
        *((_DWORD *)this + 34) |= 1u;
        v10 = (WCHAR *)MIDL_user_allocate(0x80u);
        if ( v10 )
        {
          *(_OWORD *)v10 = *((_OWORD *)this + 1);
          *((_OWORD *)v10 + 1) = *((_OWORD *)this + 2);
          *((_OWORD *)v10 + 2) = *((_OWORD *)this + 3);
          *((_OWORD *)v10 + 3) = *((_OWORD *)this + 4);
          *((_OWORD *)v10 + 4) = *((_OWORD *)this + 5);
          *((_OWORD *)v10 + 5) = *((_OWORD *)this + 6);
          *((_OWORD *)v10 + 6) = *((_OWORD *)this + 7);
          *((_OWORD *)v10 + 7) = *((_OWORD *)this + 8);
        }
        else
        {
          v10 = 0;
        }
        v11 = (WCHAR *)this[18];
        UnbiasedTime = 0;
        this[18] = v10;
        if ( v11 )
          operator delete(v11);
        utl::unique_ptr<FileHeader,utl::default_delete<FileHeader>>::~unique_ptr<FileHeader,utl::default_delete<FileHeader>>(&UnbiasedTime);
        if ( !this[18] )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, 14);
          }
          v34 = 0;
          v35 = 14;
          v36 = -1;
          pExceptionObject = 0;
          v37 = 997;
          throw (EvtException *)&pExceptionObject;
        }
        *((_BYTE *)this + 828) = 1;
      }
      v12 = (unsigned __int64)this[4];
      *(_QWORD *)&pExceptionObject = 10794;
      v34 = a4;
      File::MapInWriteChunk((File *)this, v12, a5);
      if ( !*((_BYTE *)this + 834) || (*((_BYTE *)this + 825) & 3) == 0 || (v13 = 1, *((_BYTE *)this + 835)) )
        v13 = 0;
      v14 = 2;
      v15 = this + 29;
      v16 = (LPCWSTR)((char *)this[22] + *((unsigned int *)this + 48));
      v17 = this + 29;
      if ( v13 )
        v16 -= 1024;
      this[23] = v16;
      v18 = 2;
      *((_BYTE *)this + 836) = 1;
      v19 = this[28];
      do
      {
        *v17 = *v19;
        v17[1] = v19[1];
        v17[2] = v19[2];
        v17[3] = v19[3];
        v17[4] = v19[4];
        v17[5] = v19[5];
        v17[6] = v19[6];
        v20 = v19[7];
        v19 += 8;
        v17[7] = v20;
        v17 += 8;
        --v18;
      }
      while ( v18 );
      v21 = this[63];
      *((_OWORD *)this + 32) = *v21;
      *((_OWORD *)this + 33) = v21[1];
      *((_OWORD *)this + 34) = v21[2];
      *((_OWORD *)this + 35) = v21[3];
      *((_OWORD *)this + 36) = v21[4];
      *((_OWORD *)this + 37) = v21[5];
      *((_OWORD *)this + 38) = v21[6];
      *((_OWORD *)this + 39) = v21[7];
      if ( !*((_BYTE *)this + 827) )
      {
        *((_BYTE *)this + 827) = 1;
        *((_DWORD *)this + 203) = 0;
      }
      v22 = this[5];
      v23 = *a3;
      *((_QWORD *)&pExceptionObject + 1) = v22;
      (*v23)(a3, v22, 128);
      v24 = this[20];
      LODWORD(UnbiasedTime) = 0;
      v25 = WriteFileView::SerializeBlob(
              (WriteFileView *)(this + 19),
              a2,
              (struct ObjectBlobStart *)&pExceptionObject,
              *((_DWORD *)v24 + 12),
              (unsigned int *)&UnbiasedTime);
      if ( v25 )
      {
        v29 = (WCHAR *)this[28];
        do
        {
          *(_OWORD *)v29 = *v15;
          *((_OWORD *)v29 + 1) = v15[1];
          *((_OWORD *)v29 + 2) = v15[2];
          *((_OWORD *)v29 + 3) = v15[3];
          *((_OWORD *)v29 + 4) = v15[4];
          *((_OWORD *)v29 + 5) = v15[5];
          *((_OWORD *)v29 + 6) = v15[6];
          v30 = v15[7];
          v15 += 8;
          *((_OWORD *)v29 + 7) = v30;
          v29 += 64;
          --v14;
        }
        while ( v14 );
        v31 = (WCHAR *)this[63];
        *(_OWORD *)v31 = *((_OWORD *)this + 32);
        *((_OWORD *)v31 + 1) = *((_OWORD *)this + 33);
        *((_OWORD *)v31 + 2) = *((_OWORD *)this + 34);
        *((_OWORD *)v31 + 3) = *((_OWORD *)this + 35);
        *((_OWORD *)v31 + 4) = *((_OWORD *)this + 36);
        *((_OWORD *)v31 + 5) = *((_OWORD *)this + 37);
        *((_OWORD *)v31 + 6) = *((_OWORD *)this + 38);
        *((_OWORD *)v31 + 7) = *((_OWORD *)this + 39);
      }
      else
      {
        v26 = this[20];
        v27 = *((_QWORD *)v26 + 2);
        if ( v27 == -1 )
        {
          *((_QWORD *)v26 + 2) = *((_QWORD *)v26 + 1);
          *((_QWORD *)this[20] + 3) = v22;
        }
        else
        {
          *((_QWORD *)v26 + 2) = v27 + 1;
        }
        *((_DWORD *)this[20] + 11) = *((_DWORD *)this[20] + 12);
        *((_DWORD *)this[20] + 12) += UnbiasedTime;
        *((_QWORD *)this[20] + 4) = v22;
        this[5] = (LPCWSTR)((char *)v22 + 1);
        this[98] = (LPCWSTR)*((_QWORD *)this[20] + 2);
        *((_DWORD *)this + 34) &= ~2u;
        *((_BYTE *)this + 826) = 1;
        File::PossiblyScheduleTimer(this);
        UnbiasedTime = 0;
        QueryUnbiasedInterruptTime(&UnbiasedTime);
        v28 = this[96];
        this[96] = (LPCWSTR)UnbiasedTime;
        if ( v28 == (LPCWSTR)-1LL )
          _InterlockedIncrement(&g_ActiveChannels);
      }
      return v25;
    }
    else
    {
      return 110;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003409c  push    rbp
0x18003409e  push    rbx
0x18003409f  push    rsi
0x1800340a0  push    rdi
0x1800340a1  push    r12
0x1800340a3  push    r13
0x1800340a5  push    r14
0x1800340a7  push    r15
0x1800340a9  mov     rbp, rsp
0x1800340ac  sub     rsp, 68h
0x1800340b0  mov     r13, rdx
0x1800340b3  mov     rbx, r9
0x1800340b6  mov     rdx, [rbp+arg_20]
0x1800340ba  mov     r12, r8
0x1800340bd  mov     rdi, rcx
0x1800340c0  call    ?EnsureFileIsCreated@File@@AEAAKAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::EnsureFileIsCreated(utl::unique_lock<utl::shared_mutex> &)
0x1800340c5  xor     r14d, r14d
0x1800340c8  test    eax, eax
0x1800340ca  jnz     loc_18003450C
0x1800340d0  mov     [rdi+330h], r14d
0x1800340d7  cmp     [rdi+33Dh], r14b
0x1800340de  jz      loc_180034507
0x1800340e4  cmp     [rdi+33Eh], r14b
0x1800340eb  jz      loc_180034507
0x1800340f1  mov     esi, 80h
0x1800340f6  cmp     [rdi+33Ch], r14b
0x1800340fd  jnz     loc_180034203
0x180034103  or      dword ptr [rdi+88h], 1
0x18003410a  mov     ecx, esi; size
0x18003410c  call    MIDL_user_allocate
0x180034111  test    rax, rax
0x180034114  jz      short loc_18003415A
0x180034116  movups  xmm0, xmmword ptr [rdi+10h]
0x18003411a  movups  xmmword ptr [rax], xmm0
0x18003411d  movups  xmm1, xmmword ptr [rdi+20h]
0x180034121  movups  xmmword ptr [rax+10h], xmm1
0x180034125  movups  xmm0, xmmword ptr [rdi+30h]
0x180034129  movups  xmmword ptr [rax+20h], xmm0
0x18003412d  movups  xmm1, xmmword ptr [rdi+40h]
0x180034131  movups  xmmword ptr [rax+30h], xmm1
0x180034135  movups  xmm0, xmmword ptr [rdi+50h]
0x180034139  movups  xmmword ptr [rax+40h], xmm0
0x18003413d  movups  xmm1, xmmword ptr [rdi+60h]
0x180034141  movups  xmmword ptr [rax+50h], xmm1
0x180034145  movups  xmm0, xmmword ptr [rdi+70h]
0x180034149  movups  xmmword ptr [rax+60h], xmm0
0x18003414d  movups  xmm1, xmmword ptr [rdi+80h]
0x180034154  movups  xmmword ptr [rax+70h], xmm1
0x180034158  jmp     short loc_18003415D
0x18003415a  mov     rax, r14
0x18003415d  mov     rcx, [rdi+90h]; void *
0x180034164  mov     [rbp+UnbiasedTime], r14
0x180034168  mov     [rdi+90h], rax
0x18003416f  test    rcx, rcx
0x180034172  jz      short loc_18003417C
0x180034174  mov     rdx, rsi; unsigned __int64
0x180034177  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003417c  lea     rcx, [rbp+UnbiasedTime]
0x180034180  call    ??1?$unique_ptr@UFileHeader@@U?$default_delete@UFileHeader@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<FileHeader,utl::default_delete<FileHeader>>::~unique_ptr<FileHeader,utl::default_delete<FileHeader>>(void)
0x180034185  cmp     [rdi+90h], r14
0x18003418c  jnz     short loc_1800341FC
0x18003418e  mov     rcx, cs:WPP_GLOBAL_Control
0x180034195  lea     rax, WPP_GLOBAL_Control
0x18003419c  mov     ebx, 0Eh
0x1800341a1  cmp     rcx, rax
0x1800341a4  jz      short loc_1800341CE
0x1800341a6  test    dword ptr [rcx+1Ch], 8000h
0x1800341ad  jz      short loc_1800341CE
0x1800341af  lea     esi, [rbx-0Ch]
0x1800341b2  cmp     [rcx+19h], sil
0x1800341b6  jb      short loc_1800341CE
0x1800341b8  mov     rcx, [rcx+10h]
0x1800341bc  lea     edx, [rbx+1Eh]
0x1800341bf  mov     r9d, ebx
0x1800341c2  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x1800341c9  call    WPP_SF_D
0x1800341ce  xorps   xmm0, xmm0
0x1800341d1  mov     [rbp+var_20], r14
0x1800341d5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800341dc  mov     [rbp+var_18], ebx
0x1800341df  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800341e3  mov     [rbp+var_14], 0FFFFFFFFh
0x1800341ea  movdqu  [rbp+pExceptionObject], xmm0
0x1800341ef  mov     [rbp+var_10], 3E5h
0x1800341f6  call    _CxxThrowException_0
0x1800341fc  mov     byte ptr [rdi+33Ch], 1
0x180034203  mov     r8, [rbp+arg_20]
0x180034207  mov     rcx, rdi; this
0x18003420a  mov     rdx, [rdi+20h]; unsigned __int64
0x18003420e  mov     qword ptr [rbp+pExceptionObject], 2A2Ah
0x180034216  mov     [rbp+var_20], rbx
0x18003421a  call    ?MapInWriteChunk@File@@AEAAX_KAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::MapInWriteChunk(unsigned __int64,utl::unique_lock<utl::shared_mutex> &)
0x18003421f  cmp     [rdi+342h], r14b
0x180034226  jz      short loc_18003423D
0x180034228  test    byte ptr [rdi+339h], 3
0x18003422f  jz      short loc_18003423D
0x180034231  mov     r8b, 1
0x180034234  cmp     [rdi+343h], r14b
0x18003423b  jz      short loc_180034240
0x18003423d  mov     r8b, r14b
0x180034240  lea     r15, [rdi+98h]
0x180034247  mov     esi, 2
0x18003424c  mov     edx, [r15+28h]
0x180034250  lea     rbx, [rdi+0E8h]
0x180034257  add     rdx, [r15+18h]
0x18003425b  mov     rcx, rbx
0x18003425e  test    r8b, r8b
0x180034261  lea     r8d, [rsi+7Eh]
0x180034265  lea     rax, [rdx-800h]
0x18003426c  cmovnz  rdx, rax
0x180034270  mov     [r15+20h], rdx
0x180034274  mov     edx, esi
0x180034276  mov     byte ptr [rdi+344h], 1
0x18003427d  mov     rax, [rdi+0E0h]
0x180034284  movups  xmm0, xmmword ptr [rax]
0x180034287  movups  xmmword ptr [rcx], xmm0
0x18003428a  movups  xmm1, xmmword ptr [rax+10h]
0x18003428e  movups  xmmword ptr [rcx+10h], xmm1
0x180034292  movups  xmm0, xmmword ptr [rax+20h]
0x180034296  movups  xmmword ptr [rcx+20h], xmm0
0x18003429a  movups  xmm1, xmmword ptr [rax+30h]
0x18003429e  movups  xmmword ptr [rcx+30h], xmm1
0x1800342a2  movups  xmm0, xmmword ptr [rax+40h]
0x1800342a6  movups  xmmword ptr [rcx+40h], xmm0
0x1800342aa  movups  xmm1, xmmword ptr [rax+50h]
0x1800342ae  movups  xmmword ptr [rcx+50h], xmm1
0x1800342b2  movups  xmm0, xmmword ptr [rax+60h]
0x1800342b6  movups  xmmword ptr [rcx+60h], xmm0
0x1800342ba  movups  xmm1, xmmword ptr [rax+70h]
0x1800342be  add     rax, r8
0x1800342c1  movups  xmmword ptr [rcx+70h], xmm1
0x1800342c5  add     rcx, r8
0x1800342c8  sub     rdx, 1
0x1800342cc  jnz     short loc_180034284
0x1800342ce  mov     rax, [rdi+1F8h]
0x1800342d5  movups  xmm0, xmmword ptr [rax]
0x1800342d8  movups  xmmword ptr [rdi+200h], xmm0
0x1800342df  movups  xmm1, xmmword ptr [rax+10h]
0x1800342e3  movups  xmmword ptr [rdi+210h], xmm1
0x1800342ea  movups  xmm0, xmmword ptr [rax+20h]
0x1800342ee  movups  xmmword ptr [rdi+220h], xmm0
0x1800342f5  movups  xmm1, xmmword ptr [rax+30h]
0x1800342f9  movups  xmmword ptr [rdi+230h], xmm1
0x180034300  movups  xmm0, xmmword ptr [rax+40h]
0x180034304  movups  xmmword ptr [rdi+240h], xmm0
0x18003430b  movups  xmm1, xmmword ptr [rax+50h]
0x18003430f  movups  xmmword ptr [rdi+250h], xmm1
0x180034316  movups  xmm0, xmmword ptr [rax+60h]
0x18003431a  movups  xmmword ptr [rdi+260h], xmm0
0x180034321  movups  xmm1, xmmword ptr [rax+70h]
0x180034325  movups  xmmword ptr [rdi+270h], xmm1
0x18003432c  cmp     [rdi+33Bh], r14b
0x180034333  jnz     short loc_180034343
0x180034335  mov     byte ptr [rdi+33Bh], 1
0x18003433c  mov     [rdi+32Ch], r14d
0x180034343  mov     r14, [rdi+28h]
0x180034347  mov     rcx, r12
0x18003434a  mov     rax, [r12]
0x18003434e  mov     rdx, r14
0x180034351  mov     qword ptr [rbp+pExceptionObject+8], r14
0x180034355  mov     rax, [rax]
0x180034358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003435d  mov     r9, [rdi+0A0h]
0x180034364  lea     rax, [rbp+UnbiasedTime]
0x180034368  lea     r8, [rbp+pExceptionObject]; struct ObjectBlobStart *
0x18003436c  mov     dword ptr [rbp+UnbiasedTime], 0
0x180034373  mov     rdx, r13; struct BinXmlReader *
0x180034376  mov     [rsp+68h+var_48], rax; unsigned int *
0x18003437b  mov     rcx, r15; this
0x18003437e  mov     r9d, [r9+30h]; unsigned int
0x180034382  call    ?SerializeBlob@WriteFileView@@QEAAKAEAVBinXmlReader@@PEAUObjectBlobStart@@KAEAK@Z; WriteFileView::SerializeBlob(BinXmlReader &,ObjectBlobStart *,ulong,ulong &)
0x180034387  mov     r15d, eax
0x18003438a  test    eax, eax
0x18003438c  jnz     loc_18003444E
0x180034392  mov     rdx, [rdi+0A0h]
0x180034399  mov     rax, [rdx+10h]
0x18003439d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800343a1  jnz     short loc_1800343B8
0x1800343a3  mov     rcx, [rdx+8]
0x1800343a7  mov     [rdx+10h], rcx
0x1800343ab  mov     rcx, [rdi+0A0h]
0x1800343b2  mov     [rcx+18h], r14
0x1800343b6  jmp     short loc_1800343BF
0x1800343b8  inc     rax
0x1800343bb  mov     [rdx+10h], rax
0x1800343bf  mov     rcx, [rdi+0A0h]
0x1800343c6  mov     eax, [rcx+30h]
0x1800343c9  mov     [rcx+2Ch], eax
0x1800343cc  mov     rcx, [rdi+0A0h]
0x1800343d3  mov     eax, dword ptr [rbp+UnbiasedTime]
0x1800343d6  add     [rcx+30h], eax
0x1800343d9  mov     rax, [rdi+0A0h]
0x1800343e0  mov     [rax+20h], r14
0x1800343e4  lea     rax, [r14+1]
0x1800343e8  mov     [rdi+28h], rax
0x1800343ec  mov     rax, [rdi+0A0h]
0x1800343f3  mov     rcx, [rax+10h]
0x1800343f7  mov     [rdi+310h], rcx
0x1800343fe  mov     rcx, rdi; pv
0x180034401  and     dword ptr [rdi+88h], 0FFFFFFFDh
0x180034408  mov     byte ptr [rdi+33Ah], 1
0x18003440f  call    ?PossiblyScheduleTimer@File@@AEAAXXZ; File::PossiblyScheduleTimer(void)
0x180034414  lea     rcx, [rbp+UnbiasedTime]; UnbiasedTime
0x180034418  mov     [rbp+UnbiasedTime], 0
0x180034420  call    cs:__imp_QueryUnbiasedInterruptTime
0x180034426  mov     rcx, [rdi+300h]
0x18003442d  mov     rax, [rbp+UnbiasedTime]
0x180034431  mov     [rdi+300h], rax
0x180034438  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003443c  jnz     loc_180034502
0x180034442  lock inc cs:?g_ActiveChannels@@3JA; long g_ActiveChannels
0x180034449  jmp     loc_180034502
0x18003444e  mov     rax, [rdi+0E0h]
0x180034455  mov     ecx, 80h
0x18003445a  movups  xmm0, xmmword ptr [rbx]
0x18003445d  movups  xmmword ptr [rax], xmm0
0x180034460  movups  xmm1, xmmword ptr [rbx+10h]
0x180034464  movups  xmmword ptr [rax+10h], xmm1
0x180034468  movups  xmm0, xmmword ptr [rbx+20h]
0x18003446c  movups  xmmword ptr [rax+20h], xmm0
0x180034470  movups  xmm1, xmmword ptr [rbx+30h]
0x180034474  movups  xmmword ptr [rax+30h], xmm1
0x180034478  movups  xmm0, xmmword ptr [rbx+40h]
0x18003447c  movups  xmmword ptr [rax+40h], xmm0
0x180034480  movups  xmm1, xmmword ptr [rbx+50h]
0x180034484  movups  xmmword ptr [rax+50h], xmm1
0x180034488  movups  xmm0, xmmword ptr [rbx+60h]
0x18003448c  movups  xmmword ptr [rax+60h], xmm0
0x180034490  movups  xmm1, xmmword ptr [rbx+70h]
0x180034494  add     rbx, rcx
0x180034497  movups  xmmword ptr [rax+70h], xmm1
0x18003449b  add     rax, rcx
0x18003449e  sub     rsi, 1
0x1800344a2  jnz     short loc_18003445A
0x1800344a4  movups  xmm0, xmmword ptr [rdi+200h]
0x1800344ab  mov     rax, [rdi+1F8h]
0x1800344b2  movups  xmmword ptr [rax], xmm0
0x1800344b5  movups  xmm1, xmmword ptr [rdi+210h]
0x1800344bc  movups  xmmword ptr [rax+10h], xmm1
0x1800344c0  movups  xmm0, xmmword ptr [rdi+220h]
0x1800344c7  movups  xmmword ptr [rax+20h], xmm0
0x1800344cb  movups  xmm1, xmmword ptr [rdi+230h]
0x1800344d2  movups  xmmword ptr [rax+30h], xmm1
0x1800344d6  movups  xmm0, xmmword ptr [rdi+240h]
0x1800344dd  movups  xmmword ptr [rax+40h], xmm0
0x1800344e1  movups  xmm1, xmmword ptr [rdi+250h]
0x1800344e8  movups  xmmword ptr [rax+50h], xmm1
0x1800344ec  movups  xmm0, xmmword ptr [rdi+260h]
0x1800344f3  movups  xmmword ptr [rax+60h], xmm0
0x1800344f7  movups  xmm1, xmmword ptr [rdi+270h]
0x1800344fe  movups  xmmword ptr [rax+70h], xmm1
0x180034502  mov     eax, r15d
0x180034505  jmp     short loc_18003450C
0x180034507  mov     eax, 6Eh ; 'n'
0x18003450c  add     rsp, 68h
0x180034510  pop     r15
0x180034512  pop     r14
0x180034514  pop     r13
0x180034516  pop     r12
0x180034518  pop     rdi
0x180034519  pop     rsi
0x18003451a  pop     rbx
0x18003451b  pop     rbp
0x18003451c  retn
```
