# Microsoft::Windows::Performance::CEventTraceRelogger::TraceEvent(_EVENT_TRACE *,ulong,void const *)

- ea: `0x18003f4c0`
- end: `0x18003f888`
- name: `?TraceEvent@CEventTraceRelogger@Performance@Windows@Microsoft@@UEAAJPEAU_EVENT_TRACE@@KPEBX@Z`
- size: `968`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceRelogger *this, struct _EVENT_TRACE *, unsigned int, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000829c`
- `0x18003f4c0`
- `0x18004ece0`
- `0x180082d3c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003f6ed`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003f845`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003f851`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003f6ed`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003f845`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003f851`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003f687`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003f6dd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003f687`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003f6dd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003f63d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003f63d`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x18003f79a`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x18003f80b`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x18003f79a`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x18003f80b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003f7ce`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003f7ce`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceRelogger::TraceEvent(
        Microsoft::Windows::Performance::CEventTraceRelogger *this,
        struct _EVENT_TRACE *a2,
        unsigned int a3,
        char *a4)
{
  bool v4; // zf
  size_t v7; // r13
  int v10; // eax
  unsigned int v11; // ecx
  ULONG MofLength; // edx
  unsigned int v13; // eax
  char *MofData; // rcx
  int *v15; // rbx
  int *v16; // rax
  int Size; // esi
  int *v18; // rax
  int v19; // eax
  ULONG UserTime; // eax
  USHORT v21; // cx
  unsigned int v22; // r15d
  ULONG v23; // eax
  int v24; // esi
  ULONG v25; // eax
  USHORT v26; // ax
  ULONG v27; // [rsp+30h] [rbp-79h] BYREF
  ULONG v28; // [rsp+34h] [rbp-75h]
  void *Src; // [rsp+38h] [rbp-71h] BYREF
  char *v30; // [rsp+40h] [rbp-69h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-49h] BYREF
  char *v33; // [rsp+70h] [rbp-39h]
  int v34; // [rsp+78h] [rbp-31h]
  int v35; // [rsp+7Ch] [rbp-2Dh]
  const char *v36; // [rsp+80h] [rbp-29h]
  __int64 v37; // [rsp+88h] [rbp-21h]
  void **p_Src; // [rsp+90h] [rbp-19h]
  __int64 v39; // [rsp+98h] [rbp-11h]
  char **v40; // [rsp+A0h] [rbp-9h]
  __int64 v41; // [rsp+A8h] [rbp-1h]
  ULONG *v42; // [rsp+B0h] [rbp+7h]
  __int64 v43; // [rsp+B8h] [rbp+Fh]

  v4 = *((_DWORD *)this + 4) == 4;
  v30 = a4;
  v7 = a3;
  if ( !v4 )
    return 2147947423LL;
  v10 = *((_DWORD *)this + 35);
  v11 = 65528;
  MofLength = a2->MofLength;
  v13 = v10 - 72;
  if ( v13 < 0xFFF8 )
    v11 = v13;
  if ( MofLength + a3 > v11 )
  {
    if ( (unsigned int)dword_1800BDC28 > 2
      && (qword_1800BDC38 & 0x20000000) != 0
      && (qword_1800BDC40 & 0x20000000) == qword_1800BDC40 )
    {
      v27 = a2->MofLength;
      LODWORD(v30) = 1;
      v42 = &v27;
      LODWORD(Src) = 1267;
      v40 = &v30;
      v43 = 4;
      p_Src = &Src;
      v36 = "TraceEvent";
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_1800BDC30;
      v41 = 4;
      v39 = 4;
      v37 = 11;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0x20000000;
      UserData.Size = (unsigned __int16)*off_1800BDC30;
      v33 = byte_1800A55B3;
      UserData.Reserved = 2;
      v34 = 49;
      v35 = 1;
      v28 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(qword_1800BDC48, &EventDescriptor, 0, 0, 6u, &UserData);
    }
    ++*((_DWORD *)this + 26);
    return 1;
  }
  MofData = (char *)a2->MofData;
  Src = MofData;
  if ( !a4 || !a3 )
  {
    Size = a2->Header.Size;
    if ( (((_WORD)Size - 4) & 0xFFFB) != 0 || !*((_BYTE *)this + 144) && *((_DWORD *)this + 37) != Size )
    {
      free(0);
      return 2147942487LL;
    }
    v18 = (int *)malloc(MofLength + 48);
    v15 = v18;
    if ( v18 )
    {
      LODWORD(v7) = 48;
      a2->MofData = v18 + 12;
      *(_OWORD *)v18 = 0;
      *((_OWORD *)v18 + 1) = 0;
      *((_OWORD *)v18 + 2) = 0;
      *(_OWORD *)v18 = *(_OWORD *)&a2->Header.Size;
      *((_OWORD *)v18 + 1) = *(_OWORD *)&a2->Header.TimeStamp.LowPart;
      *((_OWORD *)v18 + 2) = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&a2->Header.24 + 8);
      if ( Size == 4 || (v19 = -1072431104, !*((_BYTE *)this + 144)) )
        v19 = -1073086464;
      *v15 = v19;
      *(_WORD *)v15 = LOWORD(a2->MofLength) + 48;
      goto LABEL_27;
    }
LABEL_22:
    free(0);
    return 2147942414LL;
  }
  v15 = 0;
  if ( MofData == &a4[a3] )
    goto LABEL_28;
  if ( !MofLength )
  {
    a2->MofData = &a4[a3];
    goto LABEL_28;
  }
  v16 = (int *)malloc(MofLength + a3);
  v15 = v16;
  if ( !v16 )
    goto LABEL_22;
  a2->MofData = (char *)v16 + v7;
  memcpy_0(v16, a4, v7);
LABEL_27:
  memcpy_0(a2->MofData, Src, a2->MofLength);
LABEL_28:
  UserTime = a2->Header.UserTime;
  v21 = a2->Header.Size;
  v22 = 0;
  a2->MofLength += v7;
  v28 = UserTime;
  a2->Header.UserTime = UserTime | 0x220000;
  LOWORD(v27) = v21;
  a2->Header.Size = 88;
  a2->MofData = (char *)a2->MofData - (unsigned int)v7;
  v23 = TraceEvent(**((_QWORD **)this + 16), &a2->Header);
  v24 = ATL::AtlHresultFromWin32(v23);
  if ( v24 >= 0 )
    goto LABEL_38;
  while ( (v24 == -2147024888 || v24 == -2147024882) && v22 < *((_DWORD *)this + 25) )
  {
    ++v22;
    Sleep(0x1F4u);
LABEL_35:
    v25 = TraceEvent(**((_QWORD **)this + 16), &a2->Header);
    v24 = ATL::AtlHresultFromWin32(v25);
    if ( v24 >= 0 )
      goto LABEL_38;
  }
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, struct _EVENT_TRACE *, _QWORD, char *))(**((_QWORD **)this + 3) + 112LL))(
         *((_QWORD *)this + 3),
         (unsigned int)v24,
         a2,
         (unsigned int)v7,
         v30) >= 0 )
  {
    v22 = 0;
    goto LABEL_35;
  }
  ++*((_DWORD *)this + 26);
  v24 = 1;
LABEL_38:
  v26 = v27;
  a2->MofLength -= v7;
  a2->Header.Size = v26;
  a2->Header.UserTime = v28;
  a2->MofData = Src;
  free(v15);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x18003f4c0  push    rbp
0x18003f4c2  push    rdi
0x18003f4c3  push    r13
0x18003f4c5  push    r14
0x18003f4c7  push    r15
0x18003f4c9  lea     rbp, [rsp-37h]
0x18003f4ce  sub     rsp, 0E0h
0x18003f4d5  mov     rax, cs:__security_cookie
0x18003f4dc  xor     rax, rsp
0x18003f4df  mov     [rbp+57h+var_40], rax
0x18003f4e3  cmp     dword ptr [rcx+10h], 4
0x18003f4e7  mov     r15, r9
0x18003f4ea  mov     [rbp+57h+var_C0], r9
0x18003f4ee  mov     rdi, rdx
0x18003f4f1  mov     r13d, r8d
0x18003f4f4  mov     r14, rcx
0x18003f4f7  jz      short loc_18003F503
0x18003f4f9  mov     eax, 8007139Fh
0x18003f4fe  jmp     loc_18003F86C
0x18003f503  mov     eax, [rcx+8Ch]
0x18003f509  mov     ecx, 0FFF8h
0x18003f50e  mov     edx, [rdx+50h]
0x18003f511  add     eax, 0FFFFFFB8h
0x18003f514  cmp     eax, ecx
0x18003f516  mov     [rsp+100h+var_30], rsi
0x18003f51e  cmovb   ecx, eax
0x18003f521  lea     r8d, [rdx+r13]
0x18003f525  cmp     r8d, ecx
0x18003f528  jbe     loc_18003F64E
0x18003f52e  mov     eax, cs:dword_1800BDC28
0x18003f534  mov     esi, 1
0x18003f539  cmp     eax, 2
0x18003f53c  jbe     loc_18003F643
0x18003f542  mov     rcx, cs:qword_1800BDC40
0x18003f549  mov     rax, cs:qword_1800BDC38
0x18003f550  bt      rax, 1Dh
0x18003f555  jnb     loc_18003F643
0x18003f55b  mov     rax, rcx
0x18003f55e  and     eax, 20000000h
0x18003f563  cmp     rax, rcx
0x18003f566  jnz     loc_18003F643
0x18003f56c  mov     eax, [rdi+50h]
0x18003f56f  lea     rcx, _TraceLoggingMetadata
0x18003f576  mov     [rbp+57h+var_D0], eax
0x18003f579  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18003f57d  mov     dword ptr [rbp+57h+var_C0], esi
0x18003f580  lea     rax, [rbp+57h+var_D0]
0x18003f584  mov     [rbp+57h+var_50], rax
0x18003f588  xor     r9d, r9d; RelatedActivityId
0x18003f58b  mov     dword ptr [rbp+57h+Src], 4F3h
0x18003f592  lea     rax, [rbp+57h+var_C0]
0x18003f596  mov     [rbp+57h+var_60], rax
0x18003f59a  xor     r8d, r8d; ActivityId
0x18003f59d  mov     [rbp+57h+var_48], 4
0x18003f5a5  lea     rax, [rbp+57h+Src]
0x18003f5a9  mov     [rbp+57h+var_70], rax
0x18003f5ad  lea     rax, aTraceevent; "TraceEvent"
0x18003f5b4  mov     [rbp+57h+var_80], rax
0x18003f5b8  movzx   eax, cs:word_1800A55A9
0x18003f5bf  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18003f5c2  mov     rax, cs:off_1800BDC30
0x18003f5c9  mov     [rbp+57h+var_A0.Ptr], rax
0x18003f5cd  mov     [rbp+57h+var_58], 4
0x18003f5d5  mov     [rbp+57h+var_68], 4
0x18003f5dd  mov     [rbp+57h+var_78], 0Bh
0x18003f5e5  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18003f5ec  mov     [rbp+57h+EventDescriptor.Keyword], 20000000h
0x18003f5f4  movzx   eax, word ptr [rax]
0x18003f5f7  mov     [rbp+57h+var_A0.Size], eax
0x18003f5fa  lea     rax, byte_1800A55B3
0x18003f601  mov     [rbp+57h+var_90], rax
0x18003f605  lea     rax, _TraceLoggingMetadataEnd
0x18003f60c  sub     eax, ecx
0x18003f60e  mov     dword ptr [rbp+57h+var_A0.0Ch], 2
0x18003f615  mov     [rbp+57h+var_88], 31h ; '1'
0x18003f61c  mov     [rbp+57h+var_84], esi
0x18003f61f  mov     [rbp+57h+var_CC], eax
0x18003f622  mov     eax, [rbp+57h+var_CC]
0x18003f625  mov     rcx, cs:qword_1800BDC48; RegHandle
0x18003f62c  lea     rax, [rbp+57h+var_A0]
0x18003f630  mov     [rsp+100h+UserData], rax; UserData
0x18003f635  mov     [rsp+100h+UserDataCount], 6; UserDataCount
0x18003f63d  call    cs:__imp_EventWriteTransfer
0x18003f643  inc     dword ptr [r14+68h]
0x18003f647  mov     eax, esi
0x18003f649  jmp     loc_18003F864
0x18003f64e  mov     rcx, [rdi+48h]
0x18003f652  mov     [rbp+57h+Src], rcx
0x18003f656  mov     [rsp+100h+var_28], rbx
0x18003f65e  test    r15, r15
0x18003f661  jz      short loc_18003F6AF
0x18003f663  test    r13d, r13d
0x18003f666  jz      short loc_18003F6AF
0x18003f668  xor     ebx, ebx
0x18003f66a  lea     rax, [r9+r13]
0x18003f66e  cmp     rcx, rax
0x18003f671  jz      loc_18003F765
0x18003f677  test    edx, edx
0x18003f679  jnz     short loc_18003F684
0x18003f67b  mov     [rdi+48h], rax
0x18003f67f  jmp     loc_18003F765
0x18003f684  mov     ecx, r8d; Size
0x18003f687  call    cs:__imp_malloc
0x18003f68d  mov     rbx, rax
0x18003f690  test    rax, rax
0x18003f693  jz      short loc_18003F6EB
0x18003f695  add     rax, r13
0x18003f698  mov     r8, r13; Size
0x18003f69b  mov     rdx, r15; Src
0x18003f69e  mov     [rdi+48h], rax
0x18003f6a2  mov     rcx, rbx; void *
0x18003f6a5  call    memcpy_0
0x18003f6aa  jmp     loc_18003F754
0x18003f6af  movzx   esi, word ptr [rdi]
0x18003f6b2  mov     ecx, 0FFFBh
0x18003f6b7  lea     eax, [rsi-4]
0x18003f6ba  test    cx, ax
0x18003f6bd  jnz     loc_18003F84F
0x18003f6c3  cmp     byte ptr [r14+90h], 0
0x18003f6cb  jnz     short loc_18003F6DA
0x18003f6cd  cmp     [r14+94h], esi
0x18003f6d4  jnz     loc_18003F84F
0x18003f6da  lea     ecx, [rdx+30h]; Size
0x18003f6dd  call    cs:__imp_malloc
0x18003f6e3  mov     rbx, rax
0x18003f6e6  test    rax, rax
0x18003f6e9  jnz     short loc_18003F6FD
0x18003f6eb  xor     ecx, ecx; Block
0x18003f6ed  call    cs:__imp_free
0x18003f6f3  mov     eax, 8007000Eh
0x18003f6f8  jmp     loc_18003F85C
0x18003f6fd  xorps   xmm0, xmm0
0x18003f700  mov     r13d, 30h ; '0'
0x18003f706  add     rax, r13
0x18003f709  mov     [rdi+48h], rax
0x18003f70d  movups  xmmword ptr [rbx], xmm0
0x18003f710  movups  xmmword ptr [rbx+10h], xmm0
0x18003f714  movups  xmmword ptr [rbx+20h], xmm0
0x18003f718  movups  xmm0, xmmword ptr [rdi]
0x18003f71b  movups  xmmword ptr [rbx], xmm0
0x18003f71e  movups  xmm1, xmmword ptr [rdi+10h]
0x18003f722  movups  xmmword ptr [rbx+10h], xmm1
0x18003f726  movups  xmm0, xmmword ptr [rdi+20h]
0x18003f72a  movups  xmmword ptr [rbx+20h], xmm0
0x18003f72e  cmp     esi, 4
0x18003f731  jz      short loc_18003F742
0x18003f733  cmp     byte ptr [r14+90h], 0
0x18003f73b  mov     eax, 0C0140000h
0x18003f740  jnz     short loc_18003F747
0x18003f742  mov     eax, 0C00A0000h
0x18003f747  mov     [rbx], eax
0x18003f749  movzx   eax, word ptr [rdi+50h]
0x18003f74d  add     ax, r13w
0x18003f751  mov     [rbx], ax
0x18003f754  mov     r8d, [rdi+50h]; Size
0x18003f758  mov     rdx, [rbp+57h+Src]; Src
0x18003f75c  mov     rcx, [rdi+48h]; void *
0x18003f760  call    memcpy_0
0x18003f765  mov     eax, [rdi+2Ch]
0x18003f768  mov     rdx, rdi; EventTrace
0x18003f76b  movzx   ecx, word ptr [rdi]
0x18003f76e  xor     r15d, r15d
0x18003f771  add     [rdi+50h], r13d
0x18003f775  mov     [rbp+57h+var_CC], eax
0x18003f778  or      eax, 220000h
0x18003f77d  mov     [rdi+2Ch], eax
0x18003f780  mov     word ptr [rbp+57h+var_D0], cx
0x18003f784  mov     word ptr [rdi], 58h ; 'X'
0x18003f789  mov     eax, r13d
0x18003f78c  sub     [rdi+48h], rax
0x18003f790  mov     rcx, [r14+80h]
0x18003f797  mov     rcx, [rcx]; TraceHandle
0x18003f79a  call    cs:__imp_TraceEvent
0x18003f7a0  mov     ecx, eax; unsigned int
0x18003f7a2  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18003f7a7  mov     esi, eax
0x18003f7a9  test    eax, eax
0x18003f7ab  jns     short loc_18003F829
0x18003f7ad  nop     dword ptr [rax]
0x18003f7b0  cmp     esi, 80070008h
0x18003f7b6  jz      short loc_18003F7C0
0x18003f7b8  cmp     esi, 8007000Eh
0x18003f7be  jnz     short loc_18003F7D6
0x18003f7c0  cmp     r15d, [r14+64h]
0x18003f7c4  jnb     short loc_18003F7D6
0x18003f7c6  inc     r15d
0x18003f7c9  mov     ecx, 1F4h; dwMilliseconds
0x18003f7ce  call    cs:__imp_Sleep
0x18003f7d4  jmp     short loc_18003F7FE
0x18003f7d6  mov     rdx, [rbp+57h+var_C0]
0x18003f7da  mov     r9d, r13d
0x18003f7dd  mov     rcx, [r14+18h]
0x18003f7e1  mov     r8, rdi
0x18003f7e4  mov     qword ptr [rsp+100h+UserDataCount], rdx
0x18003f7e9  mov     edx, esi
0x18003f7eb  mov     rax, [rcx]
0x18003f7ee  mov     rax, [rax+70h]
0x18003f7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7f7  test    eax, eax
0x18003f7f9  js      short loc_18003F820
0x18003f7fb  xor     r15d, r15d
0x18003f7fe  mov     rcx, [r14+80h]
0x18003f805  mov     rdx, rdi; EventTrace
0x18003f808  mov     rcx, [rcx]; TraceHandle
0x18003f80b  call    cs:__imp_TraceEvent
0x18003f811  mov     ecx, eax; unsigned int
0x18003f813  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18003f818  mov     esi, eax
0x18003f81a  test    eax, eax
0x18003f81c  js      short loc_18003F7B0
0x18003f81e  jmp     short loc_18003F829
0x18003f820  inc     dword ptr [r14+68h]
0x18003f824  mov     esi, 1
0x18003f829  movzx   eax, word ptr [rbp+57h+var_D0]
0x18003f82d  mov     rcx, rbx; Block
0x18003f830  sub     [rdi+50h], r13d
0x18003f834  mov     [rdi], ax
0x18003f837  mov     eax, [rbp+57h+var_CC]
0x18003f83a  mov     [rdi+2Ch], eax
0x18003f83d  mov     rax, [rbp+57h+Src]
0x18003f841  mov     [rdi+48h], rax
0x18003f845  call    cs:__imp_free
0x18003f84b  mov     eax, esi
0x18003f84d  jmp     short loc_18003F85C
0x18003f84f  xor     ecx, ecx; Block
0x18003f851  call    cs:__imp_free
0x18003f857  mov     eax, 80070057h
0x18003f85c  mov     rbx, [rsp+100h+var_28]
0x18003f864  mov     rsi, [rsp+100h+var_30]
0x18003f86c  mov     rcx, [rbp+57h+var_40]
0x18003f870  xor     rcx, rsp; StackCookie
0x18003f873  call    __security_check_cookie
0x18003f878  add     rsp, 0E0h
0x18003f87f  pop     r15
0x18003f881  pop     r14
0x18003f883  pop     r13
0x18003f885  pop     rdi
0x18003f886  pop     rbp
0x18003f887  retn
```
