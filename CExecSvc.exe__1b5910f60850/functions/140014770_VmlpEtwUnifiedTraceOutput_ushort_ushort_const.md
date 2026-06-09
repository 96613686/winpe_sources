# VmlpEtwUnifiedTraceOutput(ushort,ushort const *)

- ea: `0x140014770`
- end: `0x140014ab7`
- name: `?VmlpEtwUnifiedTraceOutput@@YAXGPEBG@Z`
- size: `839`
- prototype: `void __fastcall(unsigned __int16, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x140002310`
- `0x1400026b8`
- `0x1400026fc`
- `0x140002ecc`
- `0x140014608`
- `0x140014770`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x140014a33`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x140014a7b`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x140014a33`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x140014a7b`

## pseudocode

```c
void __fastcall VmlpEtwUnifiedTraceOutput(unsigned __int16 a1, const unsigned __int16 *a2)
{
  struct _VML_ETW_TRACE *v2; // rsi
  unsigned __int64 v3; // r14
  const unsigned __int16 *v5; // rax
  __int64 v6; // r8
  signed int v7; // ecx
  __int64 v8; // rbp
  __int64 v9; // r13
  struct VmlEventDataForStackTrace *v10; // rax
  struct VmlEventDataForStackTrace *v11; // rbx
  struct _EVENT_DATA_DESCRIPTOR *v12; // rdi
  ULONG v13; // r12d
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v15; // rdx
  const unsigned __int16 *v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rdx
  const unsigned __int16 *v21; // r10
  __int64 v22; // rax
  int v23; // r8d
  int v24; // r8d
  int v25; // eax
  int v26; // edx
  void **v27; // rbp
  __int64 *v28; // rax
  __int64 v29; // rcx
  unsigned int v30; // edx
  int v31; // eax
  bool v32; // cf
  const EVENT_DESCRIPTOR *EventDescriptor; // [rsp+20h] [rbp-C8h]
  unsigned int v34; // [rsp+28h] [rbp-C0h] BYREF
  int v35; // [rsp+2Ch] [rbp-BCh] BYREF
  char v36; // [rsp+30h] [rbp-B8h] BYREF

  v2 = g_VmlEtwTrace;
  v3 = a1;
  if ( g_VmlEtwTrace )
  {
    if ( a2 )
    {
      v5 = a2;
      v6 = 1024;
      do
      {
        if ( !*v5 )
          break;
        ++v5;
        --v6;
      }
      while ( v6 );
      v7 = v6 == 0 ? 0x80070057 : 0;
      if ( v6 )
      {
        v8 = (2 * (1024 - v6)) & -(__int64)(v6 != 0);
        goto LABEL_10;
      }
    }
    else
    {
      v7 = -2147024809;
    }
    LODWORD(v8) = 0;
LABEL_10:
    if ( v7 < 0 )
      return;
    v9 = (unsigned __int16)v3 >> 14;
    EventDescriptor = (const EVENT_DESCRIPTOR *)*((_QWORD *)g_VmlEtwTrace
                                                + 128 * ((v3 >> 5) & 0x1F)
                                                + 4 * (v3 & 0x1F)
                                                + (unsigned int)v9
                                                + 39);
    if ( (v3 & 0x800) != 0 )
    {
      v10 = (struct VmlEventDataForStackTrace *)operator new(0x8D0u, (const struct std::nothrow_t *)&std::nothrow);
      v2 = g_VmlEtwTrace;
      v11 = v10;
      if ( v10 )
      {
        v12 = (struct _EVENT_DATA_DESCRIPTOR *)v10;
LABEL_16:
        v13 = 6;
        memset_0(&v12[1], 0, 0x50u);
        v12->Size = v8 + 2;
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        v12->Ptr = (ULONGLONG)a2;
        v12->Reserved = 0;
        v15 = *ThreadLocalStoragePointer;
        v16 = (const unsigned __int16 *)(*ThreadLocalStoragePointer + 2812LL);
        v17 = -1;
        v18 = -1;
        do
          ++v18;
        while ( v16[v18] );
        v19 = v15 + 2608;
        v20 = -1;
        do
          ++v20;
        while ( *(_WORD *)(v19 + 2 * v20 + 2) );
        v21 = L" - ";
        if ( v18 )
        {
          v24 = 2 * v18 + 2;
        }
        else
        {
          v22 = -1;
          do
            ++v22;
          while ( *((_WORD *)v2 + v22 + 117) );
          v23 = v22 + 1;
          if ( !v22 )
            v23 = 4;
          v16 = L" - ";
          if ( v22 )
            v16 = (const unsigned __int16 *)((char *)v2 + 234);
          v24 = 2 * v23;
        }
        v12[2].Ptr = (ULONGLONG)v16;
        v12[2].Size = v24;
        v12[2].Reserved = 0;
        if ( v20 )
        {
          v26 = 2 * v20 + 2;
          v21 = (const unsigned __int16 *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2610LL);
        }
        else
        {
          do
            ++v17;
          while ( *((_WORD *)v2 + v17 + 16) );
          v25 = v17 + 1;
          if ( v17 )
            v21 = (const unsigned __int16 *)((char *)v2 + 32);
          else
            v25 = 4;
          v26 = 2 * v25;
        }
        v12[1].Ptr = (ULONGLONG)v21;
        v12[1].Size = v26;
        v27 = 0;
        v12[1].Reserved = 0;
        v35 = 0;
        v34 = 0;
        if ( (v3 & 0x800) != 0 )
        {
          v28 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
          v29 = *v28;
          v30 = *(_DWORD *)(*v28 + 544);
          v34 = v30;
          if ( v30 )
            v27 = (void **)(v29 + 32);
          v31 = VmlpEtwInitializeModuleDescriptors(v27, v30, v11);
          v2 = g_VmlEtwTrace;
          v35 = v31;
          v13 = 4 * v31 + 6;
        }
        *(_QWORD *)&v12[3].Size = 4;
        v12[3].Ptr = (ULONGLONG)&v34;
        v32 = g_TraceLevel < (unsigned __int16)v9;
        v12[4].Size = 8 * v34;
        v12[5].Ptr = (ULONGLONG)&v35;
        v12[4].Ptr = (ULONGLONG)v27;
        v12[4].Reserved = 0;
        *(_QWORD *)&v12[5].Size = 4;
        if ( v32 || (v3 & 0x2000) != 0 )
        {
          if ( (v3 & 0x2000) != 0 )
          {
LABEL_46:
            EventWrite(*((_QWORD *)v2 + 2), *((PCEVENT_DESCRIPTOR *)v2 + v9 + 4135), v13, v12);
LABEL_47:
            if ( v11 )
              operator delete(v11);
            return;
          }
        }
        else
        {
          EventWrite(*((_QWORD *)v2 + 2), EventDescriptor, v13, v12);
          v2 = g_VmlEtwTrace;
        }
        if ( (v3 & 0x1000) == 0 || !*(_BYTE *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2608LL) )
          goto LABEL_47;
        goto LABEL_46;
      }
    }
    else
    {
      v11 = 0;
    }
    v12 = (struct _EVENT_DATA_DESCRIPTOR *)&v36;
    LOWORD(v3) = v3 & 0xF7FF;
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x140014770  push    rbx
0x140014772  push    rbp
0x140014773  push    rsi
0x140014774  push    rdi
0x140014775  push    r12
0x140014777  push    r13
0x140014779  push    r14
0x14001477b  push    r15
0x14001477d  sub     rsp, 0A8h
0x140014784  mov     rax, cs:__security_cookie
0x14001478b  xor     rax, rsp
0x14001478e  mov     [rsp+0E8h+var_58], rax
0x140014796  mov     rsi, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x14001479d  xor     edi, edi
0x14001479f  movzx   r14d, cx
0x1400147a3  mov     r15, rdx
0x1400147a6  test    rsi, rsi
0x1400147a9  jz      loc_140014A93
0x1400147af  test    rdx, rdx
0x1400147b2  jz      short loc_1400147F5
0x1400147b4  mov     r9d, 400h
0x1400147ba  mov     rax, rdx
0x1400147bd  mov     r8d, r9d
0x1400147c0  cmp     [rax], di
0x1400147c3  jz      short loc_1400147CF
0x1400147c5  add     rax, 2
0x1400147c9  sub     r8, 1
0x1400147cd  jnz     short loc_1400147C0
0x1400147cf  mov     rax, r8
0x1400147d2  neg     rax
0x1400147d5  sbb     ecx, ecx
0x1400147d7  not     ecx
0x1400147d9  and     ecx, 80070057h
0x1400147df  test    r8, r8
0x1400147e2  jz      short loc_1400147FA
0x1400147e4  sub     r9, r8
0x1400147e7  add     r9, r9
0x1400147ea  neg     r8
0x1400147ed  sbb     rbp, rbp
0x1400147f0  and     rbp, r9
0x1400147f3  jmp     short loc_1400147FD
0x1400147f5  mov     ecx, 80070057h
0x1400147fa  mov     rbp, rdi
0x1400147fd  test    ecx, ecx
0x1400147ff  js      loc_140014A93
0x140014805  movzx   eax, r14w
0x140014809  shr     ax, 0Eh
0x14001480d  movzx   r13d, ax
0x140014811  mov     eax, r14d
0x140014814  and     eax, 1Fh
0x140014817  lea     ecx, ds:0[rax*4]
0x14001481e  mov     rax, r14
0x140014821  shr     rax, 5
0x140014825  add     ecx, r13d
0x140014828  and     eax, 1Fh
0x14001482b  shl     rax, 7
0x14001482f  add     rcx, rax
0x140014832  bt      r14w, 0Bh
0x140014838  mov     rax, [rsi+rcx*8+138h]
0x140014840  mov     [rsp+0E8h+EventDescriptor], rax
0x140014845  jnb     short loc_14001486C
0x140014847  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001484e  mov     ecx, 8D0h; unsigned __int64
0x140014853  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140014858  mov     rsi, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x14001485f  mov     rbx, rax
0x140014862  test    rax, rax
0x140014865  jz      short loc_14001486F
0x140014867  mov     rdi, rax
0x14001486a  jmp     short loc_14001487D
0x14001486c  mov     rbx, rdi
0x14001486f  mov     eax, 0F7FFh
0x140014874  lea     rdi, [rsp+0E8h+var_B8]
0x140014879  and     r14w, ax
0x14001487d  mov     r12d, 6
0x140014883  lea     rcx, [rdi+10h]; void *
0x140014887  xor     edx, edx; Val
0x140014889  lea     r8d, [r12+4Ah]; Size
0x14001488e  call    memset_0
0x140014893  lea     eax, [rbp+2]
0x140014896  mov     r11d, 0A30h
0x14001489c  mov     [rdi+8], eax
0x14001489f  mov     rax, gs:58h
0x1400148a8  mov     [rdi], r15
0x1400148ab  xor     r15d, r15d
0x1400148ae  lea     r9, [r11+0CCh]
0x1400148b5  mov     [rdi+0Ch], r15d
0x1400148b9  mov     rdx, [rax]
0x1400148bc  add     r9, rdx
0x1400148bf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400148c3  mov     rax, rcx
0x1400148c6  inc     rax
0x1400148c9  cmp     [r9+rax*2], r15w
0x1400148ce  jnz     short loc_1400148C6
0x1400148d0  lea     r8, [r11+rdx]
0x1400148d4  mov     rdx, rcx
0x1400148d7  inc     rdx
0x1400148da  cmp     [r8+rdx*2+2], r15w
0x1400148e0  jnz     short loc_1400148D7
0x1400148e2  lea     r10, ?NO_VMINFO@_VML_ETW_TRACE@@2QBGB; " - "
0x1400148e9  mov     ebp, 4
0x1400148ee  test    rax, rax
0x1400148f1  jnz     short loc_140014928
0x1400148f3  lea     r11, [rsi+0EAh]
0x1400148fa  mov     rax, rcx
0x1400148fd  inc     rax
0x140014900  cmp     [r11+rax*2], r15w
0x140014905  jnz     short loc_1400148FD
0x140014907  lea     r8d, [rax+1]
0x14001490b  test    rax, rax
0x14001490e  jnz     short loc_140014913
0x140014910  mov     r8d, ebp
0x140014913  test    rax, rax
0x140014916  mov     r9, r10
0x140014919  cmovnz  r9, r11
0x14001491d  add     r8d, r8d
0x140014920  mov     r11d, 0A30h
0x140014926  jmp     short loc_140014930
0x140014928  lea     r8d, ds:2[rax*2]
0x140014930  mov     [rdi+20h], r9
0x140014934  mov     [rdi+28h], r8d
0x140014938  mov     [rdi+2Ch], r15d
0x14001493c  test    rdx, rdx
0x14001493f  jnz     short loc_140014962
0x140014941  lea     rdx, [rsi+20h]
0x140014945  inc     rcx
0x140014948  cmp     [rdx+rcx*2], r15w
0x14001494d  jnz     short loc_140014945
0x14001494f  lea     eax, [rcx+1]
0x140014952  test    rcx, rcx
0x140014955  jnz     short loc_140014959
0x140014957  mov     eax, ebp
0x140014959  cmovnz  r10, rdx
0x14001495d  lea     edx, [rax+rax]
0x140014960  jmp     short loc_14001497C
0x140014962  mov     rax, gs:58h
0x14001496b  lea     edx, ds:2[rdx*2]
0x140014972  mov     r10, [rax]
0x140014975  add     r10, 2
0x140014979  add     r10, r11
0x14001497c  bt      r14w, 0Bh
0x140014982  mov     [rdi+10h], r10
0x140014986  mov     [rdi+18h], edx
0x140014989  mov     rbp, r15
0x14001498c  mov     [rdi+1Ch], r15d
0x140014990  mov     [rsp+0E8h+var_BC], r15d
0x140014995  mov     [rsp+0E8h+var_C0], r15d
0x14001499a  jnb     short loc_1400149DE
0x14001499c  mov     rax, gs:58h
0x1400149a5  mov     edx, 220h
0x1400149aa  mov     rcx, [rax]
0x1400149ad  mov     edx, [rdx+rcx]; unsigned int
0x1400149b0  mov     [rsp+0E8h+var_C0], edx
0x1400149b4  test    edx, edx
0x1400149b6  jz      short loc_1400149C0
0x1400149b8  mov     ebp, 20h ; ' '
0x1400149bd  add     rbp, rcx
0x1400149c0  mov     r8, rbx; struct VmlEventDataForStackTrace *
0x1400149c3  mov     rcx, rbp; void **
0x1400149c6  call    ?VmlpEtwInitializeModuleDescriptors@@YAKPEAPEAXKPEAUVmlEventDataForStackTrace@@@Z; VmlpEtwInitializeModuleDescriptors(void * *,ulong,VmlEventDataForStackTrace *)
0x1400149cb  mov     rsi, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x1400149d2  mov     [rsp+0E8h+var_BC], eax
0x1400149d6  lea     r12d, ds:6[rax*4]
0x1400149de  lea     rax, [rsp+0E8h+var_C0]
0x1400149e3  mov     qword ptr [rdi+38h], 4
0x1400149eb  mov     [rdi+30h], rax
0x1400149ef  mov     eax, [rsp+0E8h+var_C0]
0x1400149f3  shl     eax, 3
0x1400149f6  cmp     cs:?g_TraceLevel@@3GA, r13w; ushort g_TraceLevel
0x1400149fe  mov     [rdi+48h], eax
0x140014a01  lea     rax, [rsp+0E8h+var_BC]
0x140014a06  mov     [rdi+50h], rax
0x140014a0a  mov     [rdi+40h], rbp
0x140014a0e  mov     [rdi+4Ch], r15d
0x140014a12  mov     qword ptr [rdi+58h], 4
0x140014a1a  jb      short loc_140014A42
0x140014a1c  bt      r14w, 0Dh
0x140014a22  jb      short loc_140014A42
0x140014a24  mov     rdx, [rsp+0E8h+EventDescriptor]; EventDescriptor
0x140014a29  mov     r9, rdi; UserData
0x140014a2c  mov     rcx, [rsi+10h]; RegHandle
0x140014a30  mov     r8d, r12d; UserDataCount
0x140014a33  call    cs:__imp_EventWrite
0x140014a39  mov     rsi, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x140014a40  jmp     short loc_140014A4A
0x140014a42  bt      r14w, 0Dh
0x140014a48  jb      short loc_140014A69
0x140014a4a  bt      r14w, 0Ch
0x140014a50  jnb     short loc_140014A81
0x140014a52  mov     rax, gs:58h
0x140014a5b  mov     rcx, [rax]
0x140014a5e  mov     eax, 0A30h
0x140014a63  cmp     [rax+rcx], r15b
0x140014a67  jz      short loc_140014A81
0x140014a69  mov     rdx, [rsi+r13*8+8138h]; EventDescriptor
0x140014a71  mov     r9, rdi; UserData
0x140014a74  mov     rcx, [rsi+10h]; RegHandle
0x140014a78  mov     r8d, r12d; UserDataCount
0x140014a7b  call    cs:__imp_EventWrite
0x140014a81  test    rbx, rbx
0x140014a84  jz      short loc_140014A93
0x140014a86  mov     edx, 8D0h; unsigned __int64
0x140014a8b  mov     rcx, rbx; void *
0x140014a8e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140014a93  mov     rcx, [rsp+0E8h+var_58]
0x140014a9b  xor     rcx, rsp; StackCookie
0x140014a9e  call    __security_check_cookie
0x140014aa3  add     rsp, 0A8h
0x140014aaa  pop     r15
0x140014aac  pop     r14
0x140014aae  pop     r13
0x140014ab0  pop     r12
0x140014ab2  pop     rdi
0x140014ab3  pop     rsi
0x140014ab4  pop     rbp
0x140014ab5  pop     rbx
0x140014ab6  retn
```
