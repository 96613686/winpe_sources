# CWMIBinMof::UpdateMofTimestampInHMOM(ushort *,ulong &,ulong &,int)

- ea: `0x180001154`
- end: `0x18000145c`
- name: `?UpdateMofTimestampInHMOM@CWMIBinMof@@QEAAHPEAGAEAK1H@Z`
- size: `776`
- prototype: `int(CWMIBinMof *__hidden this, unsigned __int16 *, unsigned int *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18000226c`
- `0x180002a5c`

## callees

- `0x180001154`
- `0x180001c54`
- `0x1800174ec`
- `0x180020010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180001194`
- `OLEAUT32!__imp_VariantInit` at `0x180001235`
- `OLEAUT32!__imp_VariantInit` at `0x180001241`
- `OLEAUT32!__imp_VariantInit` at `0x18000124c`
- `OLEAUT32!__imp_VariantInit` at `0x180001257`
- `OLEAUT32!__imp_VariantInit` at `0x180001367`
- `OLEAUT32!__imp_VariantInit` at `0x180001194`
- `OLEAUT32!__imp_VariantInit` at `0x180001235`
- `OLEAUT32!__imp_VariantInit` at `0x180001241`
- `OLEAUT32!__imp_VariantInit` at `0x18000124c`
- `OLEAUT32!__imp_VariantInit` at `0x180001257`
- `OLEAUT32!__imp_VariantInit` at `0x180001367`
- `OLEAUT32!__imp_VariantClear` at `0x180001284`
- `OLEAUT32!__imp_VariantClear` at `0x18000129e`
- `OLEAUT32!__imp_VariantClear` at `0x1800013a3`
- `OLEAUT32!__imp_VariantClear` at `0x1800013f0`
- `OLEAUT32!__imp_VariantClear` at `0x1800013fb`
- `OLEAUT32!__imp_VariantClear` at `0x180001407`
- `OLEAUT32!__imp_VariantClear` at `0x180001412`
- `OLEAUT32!__imp_VariantClear` at `0x18000141d`
- `OLEAUT32!__imp_VariantClear` at `0x180001284`
- `OLEAUT32!__imp_VariantClear` at `0x18000129e`
- `OLEAUT32!__imp_VariantClear` at `0x1800013a3`
- `OLEAUT32!__imp_VariantClear` at `0x1800013f0`
- `OLEAUT32!__imp_VariantClear` at `0x1800013fb`
- `OLEAUT32!__imp_VariantClear` at `0x180001407`
- `OLEAUT32!__imp_VariantClear` at `0x180001412`
- `OLEAUT32!__imp_VariantClear` at `0x18000141d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWMIBinMof::UpdateMofTimestampInHMOM(
        CWMIBinMof *this,
        unsigned __int16 *a2,
        LONG *a3,
        LONG *a4,
        int a5)
{
  unsigned int v9; // edi
  int v10; // r13d
  LONGLONG llVal; // rax
  int v12; // ebx
  LONG v13; // ebx
  LONG v14; // ebx
  __int64 v16; // [rsp+40h] [rbp-91h] BYREF
  VARIANTARG v17; // [rsp+48h] [rbp-89h] BYREF
  VARIANTARG v18; // [rsp+60h] [rbp-71h] BYREF
  VARIANTARG v19; // [rsp+78h] [rbp-59h] BYREF
  VARIANTARG v20; // [rsp+90h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-29h] BYREF
  VARIANTARG v22; // [rsp+C0h] [rbp-11h] BYREF
  __int64 v23; // [rsp+130h] [rbp+5Fh] BYREF

  v9 = 0;
  v23 = 0;
  v16 = 0;
  v10 = a5;
  if ( !*(_DWORD *)this )
    goto LABEL_23;
  VariantInit(&pvarg);
  CVARIANT::SetStr(&pvarg, (OLECHAR *)L"WMIBinaryMofResource");
  llVal = 0;
  if ( pvarg.vt == 8 )
    llVal = pvarg.llVal;
  v12 = (*(__int64 (__fastcall **)(_QWORD, LONGLONG, _QWORD, _QWORD, __int64 *, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 16LL)
                                                                                       + 48LL))(
          *(_QWORD *)(*((_QWORD *)this + 3) + 16LL),
          llVal,
          0,
          *(_QWORD *)(*((_QWORD *)this + 3) + 24LL),
          &v16,
          0);
  if ( !v12 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 120LL))(v16, 0, &v23);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
    if ( !v12 )
    {
      VariantInit(&v18);
      VariantInit(&v17);
      VariantInit(&v22);
      VariantInit(&v20);
      v20.vt = 11;
      v20.iVal = -(v10 != 0);
      CVARIANT::SetStr(&v22, a2);
      v13 = *a3;
      VariantClear(&v18);
      v18.vt = 3;
      v18.lVal = v13;
      v14 = *a4;
      VariantClear(&v17);
      v17.vt = 3;
      v17.lVal = v14;
      v12 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v23 + 40LL))(
              v23,
              L"Name",
              0,
              &v22,
              0);
      if ( !v12 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v23 + 40LL))(
                v23,
                L"LowDateTime",
                0,
                &v18,
                0);
        if ( !v12 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v23 + 40LL))(
                  v23,
                  L"HighDateTime",
                  0,
                  &v17,
                  0);
          if ( !v12 )
          {
            if ( !(*(unsigned int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v23 + 40LL))(
                    v23,
                    L"MofProcessed",
                    0,
                    &v20,
                    0) )
            {
              VariantInit(&v19);
              v19.vt = 11;
              v19.iVal = -1;
              (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v23 + 40LL))(
                v23,
                L"Active",
                0,
                &v19,
                0);
              VariantClear(&v19);
            }
            v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 16LL)
                                                                                     + 112LL))(
                    *(_QWORD *)(*((_QWORD *)this + 3) + 16LL),
                    v23,
                    0,
                    *(_QWORD *)(*((_QWORD *)this + 3) + 24LL),
                    0);
            if ( v23 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            v23 = 0;
          }
        }
      }
      VariantClear(&v20);
      VariantClear(&v22);
      VariantClear(&v17);
      VariantClear(&v18);
    }
  }
  VariantClear(&pvarg);
  if ( !v12 )
  {
LABEL_23:
    if ( !(unsigned int)CWMIBinMof::AddThisMofToRegistryIfNeeded(
                          this,
                          a2,
                          a2,
                          (unsigned int *)a3,
                          (unsigned int *)a4,
                          v10) )
      return 1;
  }
  return v9;
}

```

## disassembly

```asm
0x180001154  push    rbp
0x180001156  push    rbx
0x180001157  push    rsi
0x180001158  push    rdi
0x180001159  push    r12
0x18000115b  push    r13
0x18000115d  push    r14
0x18000115f  push    r15
0x180001161  lea     rbp, [rsp-17h]
0x180001166  sub     rsp, 0E8h
0x18000116d  mov     r14, r9
0x180001170  mov     r15, r8
0x180001173  mov     r12, rdx
0x180001176  mov     rsi, rcx
0x180001179  xor     edi, edi
0x18000117b  mov     [rbp+4Fh+arg_0], rdi
0x18000117f  mov     [rsp+120h+var_E0], rdi
0x180001184  mov     r13d, [rbp+4Fh+arg_20]
0x180001188  cmp     [rcx], edi
0x18000118a  jz      loc_180001427
0x180001190  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180001194  call    cs:__imp_VariantInit
0x18000119a  nop
0x18000119b  lea     rdx, aWmibinarymofre_0; "WMIBinaryMofResource"
0x1800011a2  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x1800011a6  call    ?SetStr@CVARIANT@@QEAAXPEAG@Z; CVARIANT::SetStr(ushort *)
0x1800011ab  mov     rdx, [rsi+18h]
0x1800011af  mov     rcx, [rdx+10h]
0x1800011b3  mov     rax, [rcx]
0x1800011b6  mov     r10, [rax+30h]
0x1800011ba  xor     eax, eax
0x1800011bc  cmp     word ptr [rbp+4Fh+pvarg], 8
0x1800011c1  cmovz   rax, qword ptr [rbp+4Fh+pvarg+8]
0x1800011c6  mov     qword ptr [rsp+120h+var_F8], rdi
0x1800011cb  lea     r8, [rsp+120h+var_E0]
0x1800011d0  mov     [rsp+120h+var_100], r8
0x1800011d5  mov     r9, [rdx+18h]
0x1800011d9  xor     r8d, r8d
0x1800011dc  mov     rdx, rax
0x1800011df  mov     rax, r10
0x1800011e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011e7  mov     ebx, eax
0x1800011e9  test    eax, eax
0x1800011eb  jnz     loc_180001419
0x1800011f1  mov     rcx, [rsp+120h+var_E0]
0x1800011f6  mov     rax, [rcx]
0x1800011f9  lea     r8, [rbp+4Fh+arg_0]
0x1800011fd  xor     edx, edx
0x1800011ff  mov     rax, [rax+78h]
0x180001203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001208  mov     ebx, eax
0x18000120a  mov     rcx, [rsp+120h+var_E0]
0x18000120f  test    rcx, rcx
0x180001212  jz      short loc_180001220
0x180001214  mov     rax, [rcx]
0x180001217  mov     rax, [rax+10h]
0x18000121b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001220  mov     [rsp+120h+var_E0], 0
0x180001229  test    ebx, ebx
0x18000122b  jnz     loc_180001419
0x180001231  lea     rcx, [rbp+4Fh+var_C0]; pvarg
0x180001235  call    cs:__imp_VariantInit
0x18000123b  nop
0x18000123c  lea     rcx, [rsp+120h+var_D8]; pvarg
0x180001241  call    cs:__imp_VariantInit
0x180001247  nop
0x180001248  lea     rcx, [rbp+4Fh+var_60]; pvarg
0x18000124c  call    cs:__imp_VariantInit
0x180001252  nop
0x180001253  lea     rcx, [rbp+4Fh+var_90]; pvarg
0x180001257  call    cs:__imp_VariantInit
0x18000125d  nop
0x18000125e  lea     eax, [rbx+0Bh]
0x180001261  mov     word ptr [rbp+4Fh+var_90], ax
0x180001265  mov     eax, r13d
0x180001268  neg     eax
0x18000126a  sbb     cx, cx
0x18000126d  mov     word ptr [rbp+4Fh+var_90+8], cx
0x180001271  mov     rdx, r12; psz
0x180001274  lea     rcx, [rbp+4Fh+var_60]; pvarg
0x180001278  call    ?SetStr@CVARIANT@@QEAAXPEAG@Z; CVARIANT::SetStr(ushort *)
0x18000127d  mov     ebx, [r15]
0x180001280  lea     rcx, [rbp+4Fh+var_C0]; pvarg
0x180001284  call    cs:__imp_VariantClear
0x18000128a  mov     eax, 3
0x18000128f  mov     word ptr [rbp+4Fh+var_C0], ax
0x180001293  mov     dword ptr [rbp+4Fh+var_C0+8], ebx
0x180001296  mov     ebx, [r14]
0x180001299  lea     rcx, [rsp+120h+var_D8]; pvarg
0x18000129e  call    cs:__imp_VariantClear
0x1800012a4  mov     eax, 3
0x1800012a9  mov     word ptr [rsp+120h+var_D8], ax
0x1800012ae  mov     dword ptr [rsp+120h+var_D8+8], ebx
0x1800012b2  mov     rcx, [rbp+4Fh+arg_0]
0x1800012b6  mov     rax, [rcx]
0x1800012b9  mov     dword ptr [rsp+120h+var_100], 0
0x1800012c1  lea     r9, [rbp+4Fh+var_60]
0x1800012c5  xor     r8d, r8d
0x1800012c8  lea     rdx, aName; "Name"
0x1800012cf  mov     rax, [rax+28h]
0x1800012d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012d8  mov     ebx, eax
0x1800012da  test    eax, eax
0x1800012dc  jnz     loc_1800013EC
0x1800012e2  mov     rcx, [rbp+4Fh+arg_0]
0x1800012e6  mov     rax, [rcx]
0x1800012e9  mov     dword ptr [rsp+120h+var_100], ebx
0x1800012ed  lea     r9, [rbp+4Fh+var_C0]
0x1800012f1  xor     r8d, r8d
0x1800012f4  lea     rdx, aLowdatetime; "LowDateTime"
0x1800012fb  mov     rax, [rax+28h]
0x1800012ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001304  mov     ebx, eax
0x180001306  test    eax, eax
0x180001308  jnz     loc_1800013EC
0x18000130e  mov     rcx, [rbp+4Fh+arg_0]
0x180001312  mov     rax, [rcx]
0x180001315  mov     dword ptr [rsp+120h+var_100], ebx
0x180001319  lea     r9, [rsp+120h+var_D8]
0x18000131e  xor     r8d, r8d
0x180001321  lea     rdx, aHighdatetime; "HighDateTime"
0x180001328  mov     rax, [rax+28h]
0x18000132c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001331  mov     ebx, eax
0x180001333  test    eax, eax
0x180001335  jnz     loc_1800013EC
0x18000133b  mov     rcx, [rbp+4Fh+arg_0]
0x18000133f  mov     rax, [rcx]
0x180001342  xor     ebx, ebx
0x180001344  mov     dword ptr [rsp+120h+var_100], ebx
0x180001348  lea     r9, [rbp+4Fh+var_90]
0x18000134c  xor     r8d, r8d
0x18000134f  lea     rdx, aMofprocessed; "MofProcessed"
0x180001356  mov     rax, [rax+28h]
0x18000135a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000135f  test    eax, eax
0x180001361  jnz     short loc_1800013A9
0x180001363  lea     rcx, [rbp+4Fh+var_A8]; pvarg
0x180001367  call    cs:__imp_VariantInit
0x18000136d  nop
0x18000136e  lea     eax, [rbx+0Bh]
0x180001371  mov     word ptr [rbp+4Fh+var_A8], ax
0x180001375  or      eax, 0FFFFFFFFh
0x180001378  mov     word ptr [rbp+4Fh+var_A8+8], ax
0x18000137c  mov     rcx, [rbp+4Fh+arg_0]
0x180001380  mov     rax, [rcx]
0x180001383  mov     dword ptr [rsp+120h+var_100], ebx
0x180001387  lea     r9, [rbp+4Fh+var_A8]
0x18000138b  xor     r8d, r8d
0x18000138e  lea     rdx, aActive; "Active"
0x180001395  mov     rax, [rax+28h]
0x180001399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000139e  nop
0x18000139f  lea     rcx, [rbp+4Fh+var_A8]; pvarg
0x1800013a3  call    cs:__imp_VariantClear
0x1800013a9  mov     r9, [rsi+18h]
0x1800013ad  mov     rcx, [r9+10h]
0x1800013b1  mov     rax, [rcx]
0x1800013b4  mov     [rsp+120h+var_100], rbx
0x1800013b9  mov     r9, [r9+18h]
0x1800013bd  xor     r8d, r8d
0x1800013c0  mov     rdx, [rbp+4Fh+arg_0]
0x1800013c4  mov     rax, [rax+70h]
0x1800013c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013cd  mov     ebx, eax
0x1800013cf  mov     rcx, [rbp+4Fh+arg_0]
0x1800013d3  test    rcx, rcx
0x1800013d6  jz      short loc_1800013E4
0x1800013d8  mov     rax, [rcx]
0x1800013db  mov     rax, [rax+10h]
0x1800013df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013e4  mov     [rbp+4Fh+arg_0], 0
0x1800013ec  lea     rcx, [rbp+4Fh+var_90]; pvarg
0x1800013f0  call    cs:__imp_VariantClear
0x1800013f6  nop
0x1800013f7  lea     rcx, [rbp+4Fh+var_60]; pvarg
0x1800013fb  call    cs:__imp_VariantClear
0x180001401  nop
0x180001402  lea     rcx, [rsp+120h+var_D8]; pvarg
0x180001407  call    cs:__imp_VariantClear
0x18000140d  nop
0x18000140e  lea     rcx, [rbp+4Fh+var_C0]; pvarg
0x180001412  call    cs:__imp_VariantClear
0x180001418  nop
0x180001419  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18000141d  call    cs:__imp_VariantClear
0x180001423  test    ebx, ebx
0x180001425  jnz     short loc_180001446
0x180001427  mov     [rsp+120h+var_F8], r13d; int
0x18000142c  mov     [rsp+120h+var_100], r14; unsigned int *
0x180001431  mov     r9, r15; unsigned int *
0x180001434  mov     r8, r12; unsigned __int16 *
0x180001437  call    ?AddThisMofToRegistryIfNeeded@CWMIBinMof@@QEAAJPEAG0AEAK1H@Z; CWMIBinMof::AddThisMofToRegistryIfNeeded(ushort *,ushort *,ulong &,ulong &,int)
0x18000143c  mov     ecx, 1
0x180001441  test    eax, eax
0x180001443  cmovz   edi, ecx
0x180001446  mov     eax, edi
0x180001448  add     rsp, 0E8h
0x18000144f  pop     r15
0x180001451  pop     r14
0x180001453  pop     r13
0x180001455  pop     r12
0x180001457  pop     rdi
0x180001458  pop     rsi
0x180001459  pop     rbx
0x18000145a  pop     rbp
0x18000145b  retn
```
