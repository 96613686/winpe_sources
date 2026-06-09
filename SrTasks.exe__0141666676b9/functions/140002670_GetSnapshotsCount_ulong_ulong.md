# GetSnapshotsCount(ulong *,ulong *)

- ea: `0x140002670`
- end: `0x1400029ae`
- name: `?GetSnapshotsCount@@YAJPEAK0@Z`
- size: `830`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140002ae8`

## callees

- `0x140002670`
- `0x140002e1c`
- `0x140002e84`
- `0x140006334`
- `0x14000e324`
- `0x14000e41c`
- `0x14001094e`
- `0x140010980`
- `0x140011010`

## import_xrefs

- `VSSAPI!CreateVssBackupComponentsInternal` at `0x140002754`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x140002754`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x140002810`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x140002938`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x140002810`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x140002938`

## pseudocode

```c
__int64 __fastcall GetSnapshotsCount(unsigned int *a1, unsigned int *a2)
{
  __int16 v4; // ax
  int v5; // ebx
  unsigned int v6; // esi
  unsigned int v7; // edi
  __int64 v8; // rax
  int v9; // eax
  int IsBootVolume; // eax
  unsigned int v11; // ecx
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v14; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v17; // [rsp+4Ch] [rbp-B4h]
  __int16 v18; // [rsp+4Eh] [rbp-B2h]
  GUID v19; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v21[48]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v22; // [rsp+C8h] [rbp-38h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_cc2da48973373651002ff2feee037f2e_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "GetSnapshotsCount", 112, 1);
  v14 = 0;
  v15 = 0;
  v13 = 0;
  memset_0(&v20, 0, 0x88u);
  v4 = 122;
  if ( !a1 || (v17 = 122, v4 = 123, !a2) )
  {
    v5 = -2147024809;
    v16 = -2147024809;
    goto LABEL_27;
  }
  v16 = 0;
  v17 = 123;
  *a1 = 0;
  *a2 = 0;
  v5 = CreateVssBackupComponentsInternal(&v14);
  v16 = v5;
  v4 = 127;
  if ( v5 < 0 )
    goto LABEL_27;
  v17 = 127;
  v5 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v14 + 40))(v14, 0);
  v16 = v5;
  v4 = 128;
  if ( v5 < 0 )
    goto LABEL_27;
  v17 = 128;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v14 + 280))(v14, 0xFFFFFFFFLL);
  v16 = v5;
  v4 = 129;
  if ( v5 < 0 )
    goto LABEL_27;
  v17 = 129;
  v6 = 0;
  v7 = 0;
  v8 = *v14;
  v19 = GUID_NULL;
  v9 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64, __int64, __int64 *))(v8 + 344))(v14, &v19, 1, 3, &v15);
  v5 = v9;
  if ( v9 >= 0 )
  {
    while ( 1 )
    {
      VssFreeSnapshotPropertiesInternal(v21);
      memset_0(&v20, 0, 0x88u);
      v5 = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *))(*(_QWORD *)v15 + 24LL))(v15, 1, &v20, &v13);
      v16 = v5;
      v4 = 139;
      if ( v5 < 0 )
        goto LABEL_27;
      v17 = 139;
      if ( v5 == 1 || v20 != 3 || v13 != 1 )
        goto LABEL_21;
      ++v6;
      IsBootVolume = SxIsBootVolume(v22);
      v11 = v7 + 1;
      if ( IsBootVolume )
        v11 = v7;
      v7 = v11;
    }
  }
  if ( v9 != -2147212536 )
  {
    v16 = v9;
    v4 = 170;
LABEL_27:
    v18 = v4;
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_cc2da48973373651002ff2feee037f2e_Traceguids);
LABEL_21:
  *a1 = v6;
  *a2 = v7;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_cc2da48973373651002ff2feee037f2e_Traceguids, v6, v7);
  v5 = 0;
  v16 = 0;
  v17 = 182;
LABEL_28:
  if ( v20 == 3 )
  {
    VssFreeSnapshotPropertiesInternal(v21);
    memset_0(&v20, 0, 0x88u);
    v5 = v16;
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v14 )
    (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140002670  mov     [rsp-8+arg_10], rbx
0x140002675  push    rbp
0x140002676  push    rsi
0x140002677  push    rdi
0x140002678  push    r14
0x14000267a  push    r15
0x14000267c  lea     rbp, [rsp-30h]
0x140002681  sub     rsp, 130h
0x140002688  mov     rax, cs:__security_cookie
0x14000268f  xor     rax, rsp
0x140002692  mov     [rbp+50h+var_30], rax
0x140002696  mov     r14, rdx
0x140002699  mov     r15, rcx
0x14000269c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026a3  lea     rax, WPP_GLOBAL_Control
0x1400026aa  cmp     rcx, rax
0x1400026ad  jz      short loc_1400026CD
0x1400026af  test    dword ptr [rcx+1Ch], 20000000h
0x1400026b6  jz      short loc_1400026CD
0x1400026b8  mov     rcx, [rcx+10h]
0x1400026bc  lea     r8, WPP_cc2da48973373651002ff2feee037f2e_Traceguids
0x1400026c3  mov     edx, 0Fh
0x1400026c8  call    WPP_SF_
0x1400026cd  mov     r9d, 1; unsigned __int16
0x1400026d3  lea     rdx, aGetsnapshotsco; "GetSnapshotsCount"
0x1400026da  lea     rcx, [rsp+150h+var_108]; this
0x1400026df  lea     r8d, [r9+6Fh]; unsigned __int16
0x1400026e3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1400026e8  xor     edx, edx; Val
0x1400026ea  mov     [rsp+150h+var_118], 0
0x1400026f3  mov     r8d, 88h; Size
0x1400026f9  mov     [rsp+150h+var_110], 0
0x140002702  lea     rcx, [rbp+50h+var_C0]; void *
0x140002706  mov     [rsp+150h+var_120], 0
0x14000270e  call    memset_0
0x140002713  mov     eax, 7Ah ; 'z'
0x140002718  test    r15, r15
0x14000271b  jz      loc_140002920
0x140002721  mov     [rsp+150h+var_104], ax
0x140002726  mov     eax, 7Bh ; '{'
0x14000272b  test    r14, r14
0x14000272e  jz      loc_140002920
0x140002734  mov     [rsp+150h+var_108], 0
0x14000273c  lea     rcx, [rsp+150h+var_118]
0x140002741  mov     [rsp+150h+var_104], ax
0x140002746  mov     dword ptr [r15], 0
0x14000274d  mov     dword ptr [r14], 0
0x140002754  call    cs:__imp_CreateVssBackupComponentsInternal
0x14000275a  mov     ebx, eax
0x14000275c  mov     [rsp+150h+var_108], eax
0x140002760  test    eax, eax
0x140002762  mov     eax, 7Fh
0x140002767  js      loc_140002929
0x14000276d  mov     rcx, [rsp+150h+var_118]
0x140002772  xor     edx, edx
0x140002774  mov     [rsp+150h+var_104], ax
0x140002779  mov     rax, [rcx]
0x14000277c  mov     rax, [rax+28h]
0x140002780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002785  mov     ebx, eax
0x140002787  mov     [rsp+150h+var_108], eax
0x14000278b  test    eax, eax
0x14000278d  mov     eax, 80h
0x140002792  js      loc_140002929
0x140002798  mov     rcx, [rsp+150h+var_118]
0x14000279d  or      edx, 0FFFFFFFFh
0x1400027a0  mov     [rsp+150h+var_104], ax
0x1400027a5  mov     rax, [rcx]
0x1400027a8  mov     rax, [rax+118h]
0x1400027af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027b4  mov     ebx, eax
0x1400027b6  mov     [rsp+150h+var_108], eax
0x1400027ba  test    eax, eax
0x1400027bc  mov     eax, 81h
0x1400027c1  js      loc_140002929
0x1400027c7  mov     rcx, [rsp+150h+var_118]
0x1400027cc  lea     rdx, [rsp+150h+var_110]
0x1400027d1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400027d8  mov     [rsp+150h+var_104], ax
0x1400027dd  xor     esi, esi
0x1400027df  mov     [rsp+150h+var_130], rdx
0x1400027e4  xor     edi, edi
0x1400027e6  mov     rax, [rcx]
0x1400027e9  lea     rdx, [rbp+50h+var_D0]
0x1400027ed  movdqu  [rbp+50h+var_D0], xmm0
0x1400027f2  lea     r9d, [rsi+3]
0x1400027f6  lea     r8d, [rsi+1]
0x1400027fa  mov     rax, [rax+158h]
0x140002801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002806  mov     ebx, eax
0x140002808  test    eax, eax
0x14000280a  js      short loc_140002887
0x14000280c  lea     rcx, [rbp+50h+var_B8]
0x140002810  call    cs:__imp_VssFreeSnapshotPropertiesInternal
0x140002816  xor     edx, edx; Val
0x140002818  lea     rcx, [rbp+50h+var_C0]; void *
0x14000281c  mov     r8d, 88h; Size
0x140002822  call    memset_0
0x140002827  mov     rcx, [rsp+150h+var_110]
0x14000282c  lea     r9, [rsp+150h+var_120]
0x140002831  lea     r8, [rbp+50h+var_C0]
0x140002835  mov     edx, 1
0x14000283a  mov     rax, [rcx]
0x14000283d  mov     rax, [rax+18h]
0x140002841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002846  mov     ebx, eax
0x140002848  mov     [rsp+150h+var_108], eax
0x14000284c  test    eax, eax
0x14000284e  mov     eax, 8Bh
0x140002853  js      loc_140002929
0x140002859  mov     [rsp+150h+var_104], ax
0x14000285e  cmp     ebx, 1
0x140002861  jz      short loc_1400028C5
0x140002863  cmp     [rbp+50h+var_C0], 3
0x140002867  jnz     short loc_1400028C5
0x140002869  cmp     [rsp+150h+var_120], 1
0x14000286e  jnz     short loc_1400028C5
0x140002870  mov     rcx, [rbp+50h+var_88]; unsigned __int16 *
0x140002874  inc     esi
0x140002876  call    ?SxIsBootVolume@@YAJPEBG@Z; SxIsBootVolume(ushort const *)
0x14000287b  lea     ecx, [rdi+1]
0x14000287e  test    eax, eax
0x140002880  cmovnz  ecx, edi
0x140002883  mov     edi, ecx
0x140002885  jmp     short loc_14000280C
0x140002887  cmp     eax, 80042308h
0x14000288c  jnz     loc_140002915
0x140002892  mov     rcx, cs:WPP_GLOBAL_Control
0x140002899  lea     rbx, WPP_GLOBAL_Control
0x1400028a0  cmp     rcx, rbx
0x1400028a3  jz      short loc_1400028CC
0x1400028a5  test    dword ptr [rcx+1Ch], 8000000h
0x1400028ac  jz      short loc_1400028CC
0x1400028ae  mov     rcx, [rcx+10h]
0x1400028b2  lea     r8, WPP_cc2da48973373651002ff2feee037f2e_Traceguids
0x1400028b9  mov     edx, 10h
0x1400028be  call    WPP_SF_
0x1400028c3  jmp     short loc_1400028CC
0x1400028c5  lea     rbx, WPP_GLOBAL_Control
0x1400028cc  mov     [r15], esi
0x1400028cf  mov     [r14], edi
0x1400028d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400028d9  cmp     rcx, rbx
0x1400028dc  jz      short loc_140002903
0x1400028de  test    dword ptr [rcx+1Ch], 8000000h
0x1400028e5  jz      short loc_140002903
0x1400028e7  mov     rcx, [rcx+10h]
0x1400028eb  lea     r8, WPP_cc2da48973373651002ff2feee037f2e_Traceguids
0x1400028f2  mov     edx, 11h
0x1400028f7  mov     dword ptr [rsp+150h+var_130], edi
0x1400028fb  mov     r9d, esi
0x1400028fe  call    WPP_SF_dd
0x140002903  xor     ebx, ebx
0x140002905  mov     eax, 0B6h
0x14000290a  mov     [rsp+150h+var_108], ebx
0x14000290e  mov     [rsp+150h+var_104], ax
0x140002913  jmp     short loc_14000292E
0x140002915  mov     [rsp+150h+var_108], eax
0x140002919  mov     eax, 0AAh
0x14000291e  jmp     short loc_140002929
0x140002920  mov     ebx, 80070057h
0x140002925  mov     [rsp+150h+var_108], ebx
0x140002929  mov     [rsp+150h+var_102], ax
0x14000292e  cmp     [rbp+50h+var_C0], 3
0x140002932  jnz     short loc_140002953
0x140002934  lea     rcx, [rbp+50h+var_B8]
0x140002938  call    cs:__imp_VssFreeSnapshotPropertiesInternal
0x14000293e  xor     edx, edx; Val
0x140002940  lea     rcx, [rbp+50h+var_C0]; void *
0x140002944  mov     r8d, 88h; Size
0x14000294a  call    memset_0
0x14000294f  mov     ebx, [rsp+150h+var_108]
0x140002953  mov     rcx, [rsp+150h+var_110]
0x140002958  test    rcx, rcx
0x14000295b  jz      short loc_140002969
0x14000295d  mov     rax, [rcx]
0x140002960  mov     rax, [rax+10h]
0x140002964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002969  mov     rcx, [rsp+150h+var_118]
0x14000296e  test    rcx, rcx
0x140002971  jz      short loc_14000297F
0x140002973  mov     rdx, [rcx]
0x140002976  mov     rax, [rdx+10h]
0x14000297a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000297f  lea     rcx, [rsp+150h+var_108]; this
0x140002984  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140002989  mov     eax, ebx
0x14000298b  mov     rcx, [rbp+50h+var_30]
0x14000298f  xor     rcx, rsp; StackCookie
0x140002992  call    __security_check_cookie
0x140002997  mov     rbx, [rsp+150h+arg_10]
0x14000299f  add     rsp, 130h
0x1400029a6  pop     r15
0x1400029a8  pop     r14
0x1400029aa  pop     rdi
0x1400029ab  pop     rsi
0x1400029ac  pop     rbp
0x1400029ad  retn
```
