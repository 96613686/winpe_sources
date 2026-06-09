# CItemIDFactory<tagPUBITEM,1279415632>::s_CreateItemID(tagPUBITEM const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)

- ea: `0x180044730`
- end: `0x1800448f6`
- name: `?s_CreateItemID@?$CItemIDFactory@UtagPUBITEM@@$0EMECFFFA@@@SAJPEFBUtagPUBITEM@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800440dc`

## callees

- `0x180005406`
- `0x180044730`
- `0x1800582a2`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800448dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800448dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800448a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800448a4`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<tagPUBITEM,1279415632>::s_CreateItemID(
        _OWORD *a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 *a3,
        __int64 a4)
{
  int v4; // eax
  int v8; // ebx
  __int64 v9; // r14
  __int64 v10; // rbx
  __int64 v11; // rcx
  _OWORD *v12; // rax
  __int128 v13; // xmm1
  __int16 v14; // si
  void *v15; // rax
  void *Src; // [rsp+20h] [rbp-10h] BYREF
  size_t Size; // [rsp+68h] [rbp+38h] BYREF
  __int64 v19; // [rsp+70h] [rbp+40h] BYREF

  v4 = 0;
  *a3 = 0;
  Src = 0;
  LODWORD(Size) = 0;
  if ( !a2 )
  {
LABEL_5:
    v9 = (unsigned int)(v4 + 552) + 2LL;
    if ( a4 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a4 + 24LL))(a4, (unsigned int)(v4 + 552) + 2LL);
    }
    else
    {
      v14 = v4 + 562;
      if ( (unsigned __int64)(unsigned int)(v4 + 552) + 10 > 0x10001 )
        goto LABEL_18;
      v15 = CoTaskMemAlloc((unsigned int)(v4 + 552) + 10LL);
      v10 = (__int64)v15;
      if ( v15 )
      {
        memset_0(v15, 0, v9 + 8);
        *(_WORD *)(v10 + 4) = v9;
        *(_WORD *)v10 = v14 - 2;
        goto LABEL_8;
      }
    }
    if ( v10 )
    {
LABEL_8:
      *(_DWORD *)(v10 + 6) = 1279415632;
      *(_WORD *)(v10 + 10) = Size;
      *(_WORD *)(v10 + 12) = 544;
      if ( a1 )
      {
        v11 = 4;
        v12 = (_OWORD *)(v10 + 14);
        do
        {
          *v12 = *a1;
          v12[1] = a1[1];
          v12[2] = a1[2];
          v12[3] = a1[3];
          v12[4] = a1[4];
          v12[5] = a1[5];
          v12[6] = a1[6];
          v13 = a1[7];
          a1 += 8;
          v12[7] = v13;
          v12 += 8;
          --v11;
        }
        while ( v11 );
        *v12 = *a1;
        v12[1] = a1[1];
      }
      if ( Src )
        memcpy_0((void *)(v10 + 558), Src, (unsigned int)Size);
      *a3 = v10;
      v8 = 0;
      goto LABEL_19;
    }
LABEL_18:
    v8 = -2147024882;
LABEL_19:
    CoTaskMemFree(Src);
    return (unsigned int)v8;
  }
  v19 = 0;
  v8 = (**a2)(a2, &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &v19);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, void **, size_t *))(*(_QWORD *)v19 + 40LL))(v19, &Src, &Size);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v8 >= 0 )
    {
      v4 = Size;
      goto LABEL_5;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180044730  mov     [rsp-28h+arg_0], rbx
0x180044735  push    rbp
0x180044736  push    rsi
0x180044737  push    rdi
0x180044738  push    r14
0x18004473a  push    r15
0x18004473c  mov     rbp, rsp
0x18004473f  sub     rsp, 30h
0x180044743  xor     eax, eax
0x180044745  mov     qword ptr [r8], 0
0x18004474c  mov     [rbp+Src], 0
0x180044754  mov     rsi, r9
0x180044757  mov     dword ptr [rbp+Size], eax
0x18004475a  mov     r15, r8
0x18004475d  mov     r10, rdx
0x180044760  mov     rdi, rcx
0x180044763  test    rdx, rdx
0x180044766  jz      short loc_1800447C4
0x180044768  mov     [rbp+arg_10], rax
0x18004476c  lea     r8, [rbp+arg_10]
0x180044770  mov     rax, [rdx]
0x180044773  mov     rcx, r10
0x180044776  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x18004477d  mov     rax, [rax]
0x180044780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044785  mov     ebx, eax
0x180044787  test    eax, eax
0x180044789  js      loc_1800448E3
0x18004478f  mov     rcx, [rbp+arg_10]
0x180044793  lea     r8, [rbp+Size]
0x180044797  lea     rdx, [rbp+Src]
0x18004479b  mov     rax, [rcx]
0x18004479e  mov     rax, [rax+28h]
0x1800447a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447a7  mov     rcx, [rbp+arg_10]
0x1800447ab  mov     ebx, eax
0x1800447ad  mov     rax, [rcx]
0x1800447b0  mov     rax, [rax+10h]
0x1800447b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447b9  test    ebx, ebx
0x1800447bb  js      loc_1800448E3
0x1800447c1  mov     eax, dword ptr [rbp+Size]
0x1800447c4  lea     r14d, [rax+228h]
0x1800447cb  add     r14, 2
0x1800447cf  test    rsi, rsi
0x1800447d2  jz      loc_180044894
0x1800447d8  mov     rax, [rsi]
0x1800447db  mov     rdx, r14
0x1800447de  mov     rcx, rsi
0x1800447e1  mov     rax, [rax+18h]
0x1800447e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447ea  mov     rbx, rax
0x1800447ed  test    rbx, rbx
0x1800447f0  jz      loc_1800448D4
0x1800447f6  mov     dword ptr [rbx+6], 4C425550h
0x1800447fd  movzx   eax, word ptr [rbp+Size]
0x180044801  mov     [rbx+0Ah], ax
0x180044805  mov     word ptr [rbx+0Ch], 220h
0x18004480b  test    rdi, rdi
0x18004480e  jz      short loc_180044874
0x180044810  mov     ecx, 4
0x180044815  lea     rax, [rbx+0Eh]
0x180044819  lea     edx, [rcx+7Ch]
0x18004481c  movups  xmm0, xmmword ptr [rdi]
0x18004481f  movups  xmmword ptr [rax], xmm0
0x180044822  movups  xmm1, xmmword ptr [rdi+10h]
0x180044826  movups  xmmword ptr [rax+10h], xmm1
0x18004482a  movups  xmm0, xmmword ptr [rdi+20h]
0x18004482e  movups  xmmword ptr [rax+20h], xmm0
0x180044832  movups  xmm1, xmmword ptr [rdi+30h]
0x180044836  movups  xmmword ptr [rax+30h], xmm1
0x18004483a  movups  xmm0, xmmword ptr [rdi+40h]
0x18004483e  movups  xmmword ptr [rax+40h], xmm0
0x180044842  movups  xmm1, xmmword ptr [rdi+50h]
0x180044846  movups  xmmword ptr [rax+50h], xmm1
0x18004484a  movups  xmm0, xmmword ptr [rdi+60h]
0x18004484e  movups  xmmword ptr [rax+60h], xmm0
0x180044852  movups  xmm1, xmmword ptr [rdi+70h]
0x180044856  add     rdi, rdx
0x180044859  movups  xmmword ptr [rax+70h], xmm1
0x18004485d  add     rax, rdx
0x180044860  sub     rcx, 1
0x180044864  jnz     short loc_18004481C
0x180044866  movups  xmm0, xmmword ptr [rdi]
0x180044869  movups  xmmword ptr [rax], xmm0
0x18004486c  movups  xmm1, xmmword ptr [rdi+10h]
0x180044870  movups  xmmword ptr [rax+10h], xmm1
0x180044874  mov     rdx, [rbp+Src]; Src
0x180044878  test    rdx, rdx
0x18004487b  jz      short loc_18004488D
0x18004487d  mov     r8d, dword ptr [rbp+Size]; Size
0x180044881  lea     rcx, [rbx+22Eh]; void *
0x180044888  call    memcpy_0
0x18004488d  mov     [r15], rbx
0x180044890  xor     ebx, ebx
0x180044892  jmp     short loc_1800448D9
0x180044894  lea     rsi, [r14+8]
0x180044898  cmp     rsi, 10001h
0x18004489f  ja      short loc_1800448D4
0x1800448a1  mov     rcx, rsi; cb
0x1800448a4  call    cs:__imp_CoTaskMemAlloc
0x1800448aa  mov     rbx, rax
0x1800448ad  test    rax, rax
0x1800448b0  jz      loc_1800447ED
0x1800448b6  mov     r8, rsi; Size
0x1800448b9  xor     edx, edx; Val
0x1800448bb  mov     rcx, rax; void *
0x1800448be  call    memset_0
0x1800448c3  sub     si, 2
0x1800448c7  mov     [rbx+4], r14w
0x1800448cc  mov     [rbx], si
0x1800448cf  jmp     loc_1800447F6
0x1800448d4  mov     ebx, 8007000Eh
0x1800448d9  mov     rcx, [rbp+Src]; pv
0x1800448dd  call    cs:__imp_CoTaskMemFree
0x1800448e3  mov     eax, ebx
0x1800448e5  mov     rbx, [rsp+30h+arg_0]
0x1800448ea  add     rsp, 30h
0x1800448ee  pop     r15
0x1800448f0  pop     r14
0x1800448f2  pop     rdi
0x1800448f3  pop     rsi
0x1800448f4  pop     rbp
0x1800448f5  retn
```
