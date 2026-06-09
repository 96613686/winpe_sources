# StructuredQuery1::CompoundCondition::Save(IStream *,int)

- ea: `0x180037530`
- end: `0x180037736`
- name: `?Save@CompoundCondition@StructuredQuery1@@UEAAJPEAUIStream@@H@Z`
- size: `518`
- prototype: `int(StructuredQuery1::CompoundCondition *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180037530`
- `0x180037d50`
- `0x18005daf0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037580`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800375c8`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800376a1`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037580`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800375c8`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800376a1`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::CompoundCondition::Save(
        StructuredQuery1::CompoundCondition *this,
        struct IStream *a2,
        int a3)
{
  HRESULT v5; // ebx
  __int64 v6; // rcx
  HRESULT v7; // eax
  unsigned int v8; // esi
  __int64 v9; // rcx
  __int64 i; // rcx
  _QWORD *v11; // rdx
  __int64 v12; // rax
  unsigned int pv; // [rsp+30h] [rbp-30h] BYREF
  __int64 v15; // [rsp+38h] [rbp-28h] BYREF
  __int64 v16; // [rsp+40h] [rbp-20h] BYREF
  __int128 v17; // [rsp+48h] [rbp-18h] BYREF

  if ( !a2 )
    return (unsigned int)-2147024809;
  v5 = StructuredQuery1::BaseCondition::Save(this, a2, a3);
  if ( v5 >= 0 )
  {
    v5 = IStream_Write(a2, (char *)this + 48, 4u);
    if ( v5 >= 0 )
    {
      v6 = *((_QWORD *)this + 7);
      pv = 0;
      if ( v6 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v6 + 24LL))(v6, &pv);
        if ( v5 < 0 )
          return (unsigned int)v5;
      }
      else
      {
        pv = -1;
      }
      v7 = IStream_Write(a2, &pv, 4u);
      v5 = v7;
      if ( *((_QWORD *)this + 7) )
      {
        v8 = 0;
        if ( v7 >= 0 )
        {
          do
          {
            if ( v8 >= pv )
              break;
            v9 = *((_QWORD *)this + 7);
            v16 = 0;
            v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v9 + 32LL))(
                   v9,
                   v8,
                   &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                   &v16);
            if ( v5 >= 0 )
            {
              v15 = 0;
              v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v16)(
                     v16,
                     &GUID_00000109_0000_0000_c000_000000000046,
                     &v15);
              if ( v5 >= 0 )
              {
                v17 = 0;
                v5 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v15 + 24LL))(v15, &v17);
                if ( v5 >= 0 )
                {
                  for ( i = 0; ; i = (unsigned int)(i + 1) )
                  {
                    if ( (unsigned int)i >= 3 )
                    {
                      v5 = -2147024809;
                      goto LABEL_19;
                    }
                    v11 = (_QWORD *)*((_QWORD *)&g_rgClassIdCondition.Data1 + i);
                    v12 = *v11 - v17;
                    if ( *v11 == (_QWORD)v17 )
                      v12 = v11[1] - *((_QWORD *)&v17 + 1);
                    if ( !v12 )
                      break;
                  }
                  v5 = IStream_Write(a2, &v17, 0x10u);
                  if ( v5 >= 0 )
                    v5 = (*(__int64 (__fastcall **)(__int64, struct IStream *, __int64))(*(_QWORD *)v15 + 48LL))(
                           v15,
                           a2,
                           1);
                }
LABEL_19:
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
            }
            ++v8;
          }
          while ( v5 >= 0 );
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180037530  mov     [rsp-18h+arg_10], rbx
0x180037535  mov     [rsp-18h+arg_18], rsi
0x18003753a  push    rbp
0x18003753b  push    rdi
0x18003753c  push    r14
0x18003753e  mov     rbp, rsp
0x180037541  sub     rsp, 60h
0x180037545  mov     rax, cs:__security_cookie
0x18003754c  xor     rax, rsp
0x18003754f  mov     [rbp+var_8], rax
0x180037553  mov     rdi, rdx
0x180037556  mov     r14, rcx
0x180037559  test    rdx, rdx
0x18003755c  jz      loc_180037723
0x180037562  call    ?Save@BaseCondition@StructuredQuery1@@UEAAJPEAUIStream@@H@Z; StructuredQuery1::BaseCondition::Save(IStream *,int)
0x180037567  mov     ebx, eax
0x180037569  test    eax, eax
0x18003756b  js      loc_1800376F2
0x180037571  mov     esi, 4
0x180037576  lea     rdx, [r14+30h]; pv
0x18003757a  mov     r8d, esi; cb
0x18003757d  mov     rcx, rdi; pstm
0x180037580  call    cs:__imp_IStream_Write
0x180037586  mov     ebx, eax
0x180037588  test    eax, eax
0x18003758a  js      loc_1800376F2
0x180037590  mov     rcx, [r14+38h]
0x180037594  mov     [rbp+pv], 0
0x18003759b  test    rcx, rcx
0x18003759e  jz      loc_18003772A
0x1800375a4  mov     rax, [rcx]
0x1800375a7  lea     rdx, [rbp+pv]
0x1800375ab  mov     rax, [rax+18h]
0x1800375af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375b4  mov     ebx, eax
0x1800375b6  test    eax, eax
0x1800375b8  js      loc_1800376F2
0x1800375be  mov     r8d, esi; cb
0x1800375c1  lea     rdx, [rbp+pv]; pv
0x1800375c5  mov     rcx, rdi; pstm
0x1800375c8  call    cs:__imp_IStream_Write
0x1800375ce  cmp     qword ptr [r14+38h], 0
0x1800375d3  mov     ebx, eax
0x1800375d5  jz      loc_1800376F2
0x1800375db  xor     esi, esi
0x1800375dd  test    eax, eax
0x1800375df  js      loc_1800376F2
0x1800375e5  cmp     esi, [rbp+pv]
0x1800375e8  jnb     loc_1800376F2
0x1800375ee  mov     rcx, [r14+38h]
0x1800375f2  lea     r9, [rbp+var_20]
0x1800375f6  mov     [rbp+var_20], 0
0x1800375fe  lea     r8, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x180037605  mov     edx, esi
0x180037607  mov     rax, [rcx]
0x18003760a  mov     rax, [rax+20h]
0x18003760e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037613  mov     ebx, eax
0x180037615  test    eax, eax
0x180037617  js      loc_1800376E8
0x18003761d  mov     rcx, [rbp+var_20]
0x180037621  lea     r8, [rbp+var_28]
0x180037625  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18003762c  mov     [rbp+var_28], 0
0x180037634  mov     rax, [rcx]
0x180037637  mov     rax, [rax]
0x18003763a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003763f  mov     ebx, eax
0x180037641  test    eax, eax
0x180037643  js      loc_1800376D8
0x180037649  mov     rcx, [rbp+var_28]
0x18003764d  lea     rdx, [rbp+var_18]
0x180037651  xorps   xmm0, xmm0
0x180037654  movups  [rbp+var_18], xmm0
0x180037658  mov     rax, [rcx]
0x18003765b  mov     rax, [rax+18h]
0x18003765f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037664  mov     ebx, eax
0x180037666  test    eax, eax
0x180037668  js      short loc_1800376C8
0x18003766a  xor     ecx, ecx
0x18003766c  cmp     ecx, 3
0x18003766f  jnb     loc_18003771C
0x180037675  lea     rdx, ?g_rgClassIdCondition@@3QBQEBU_GUID@@B; _GUID const * const near * const g_rgClassIdCondition
0x18003767c  mov     rdx, [rdx+rcx*8]
0x180037680  mov     rax, [rdx]
0x180037683  sub     rax, qword ptr [rbp+var_18]
0x180037687  jnz     short loc_180037691
0x180037689  mov     rax, [rdx+8]
0x18003768d  sub     rax, qword ptr [rbp+var_18+8]
0x180037691  test    rax, rax
0x180037694  jnz     short loc_180037715
0x180037696  lea     r8d, [rax+10h]; cb
0x18003769a  mov     rcx, rdi; pstm
0x18003769d  lea     rdx, [rbp+var_18]; pv
0x1800376a1  call    cs:__imp_IStream_Write
0x1800376a7  mov     ebx, eax
0x1800376a9  test    eax, eax
0x1800376ab  js      short loc_1800376C8
0x1800376ad  mov     rcx, [rbp+var_28]
0x1800376b1  mov     r8d, 1
0x1800376b7  mov     rdx, rdi
0x1800376ba  mov     rax, [rcx]
0x1800376bd  mov     rax, [rax+30h]
0x1800376c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376c6  mov     ebx, eax
0x1800376c8  mov     rcx, [rbp+var_28]
0x1800376cc  mov     rax, [rcx]
0x1800376cf  mov     rax, [rax+10h]
0x1800376d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376d8  mov     rcx, [rbp+var_20]
0x1800376dc  mov     rax, [rcx]
0x1800376df  mov     rax, [rax+10h]
0x1800376e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376e8  inc     esi
0x1800376ea  test    ebx, ebx
0x1800376ec  jns     loc_1800375E5
0x1800376f2  mov     eax, ebx
0x1800376f4  mov     rcx, [rbp+var_8]
0x1800376f8  xor     rcx, rsp; StackCookie
0x1800376fb  call    __security_check_cookie
0x180037700  lea     r11, [rsp+60h+var_s0]
0x180037705  mov     rbx, [r11+30h]
0x180037709  mov     rsi, [r11+38h]
0x18003770d  mov     rsp, r11
0x180037710  pop     r14
0x180037712  pop     rdi
0x180037713  pop     rbp
0x180037714  retn
0x180037715  inc     ecx
0x180037717  jmp     loc_18003766C
0x18003771c  mov     ebx, 80070057h
0x180037721  jmp     short loc_1800376C8
0x180037723  mov     ebx, 80070057h
0x180037728  jmp     short loc_1800376F2
0x18003772a  mov     [rbp+pv], 0FFFFFFFFh
0x180037731  jmp     loc_1800375BE
```
