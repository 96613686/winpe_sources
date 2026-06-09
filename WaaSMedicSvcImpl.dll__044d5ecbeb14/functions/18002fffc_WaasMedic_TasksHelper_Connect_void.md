# WaasMedic::TasksHelper::Connect(void)

- ea: `0x18002fffc`
- end: `0x1800301d9`
- name: `?Connect@TasksHelper@WaasMedic@@AEAAJXZ`
- size: `477`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180032c94`

## callees

- `0x18002e81c`
- `0x18002fffc`
- `0x1800639bc`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180030089`
- `OLEAUT32!__imp_VariantInit` at `0x1800300a1`
- `OLEAUT32!__imp_VariantInit` at `0x1800300ba`
- `OLEAUT32!__imp_VariantInit` at `0x1800300d1`
- `OLEAUT32!__imp_VariantInit` at `0x180030089`
- `OLEAUT32!__imp_VariantInit` at `0x1800300a1`
- `OLEAUT32!__imp_VariantInit` at `0x1800300ba`
- `OLEAUT32!__imp_VariantInit` at `0x1800300d1`
- `OLEAUT32!__imp_VariantClear` at `0x180030132`
- `OLEAUT32!__imp_VariantClear` at `0x180030145`
- `OLEAUT32!__imp_VariantClear` at `0x180030154`
- `OLEAUT32!__imp_VariantClear` at `0x180030163`
- `OLEAUT32!__imp_VariantClear` at `0x180030132`
- `OLEAUT32!__imp_VariantClear` at `0x180030145`
- `OLEAUT32!__imp_VariantClear` at `0x180030154`
- `OLEAUT32!__imp_VariantClear` at `0x180030163`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030055`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030055`

## string_xrefs

- `0x180030179`: `Error when connecting to Task Scheduler. hr=0x%08x`
- `0x180030064`: `Unable to CoCreateInstance for Task Scheduler. hr=0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WaasMedic::TasksHelper::Connect(LPVOID *ppv)
{
  int v2; // ebx
  HRESULT Instance; // eax
  LPVOID v4; // rdi
  __int64 (__fastcall *v5)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v6; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v8; // xmm8
  IRecordInfo *v9; // xmm9_8
  __int128 v10; // xmm6
  IRecordInfo *v11; // xmm7_8
  HRESULT v12; // eax
  HRESULT v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // eax
  VARIANTARG v17; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG v18; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v19; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  __int128 v21; // [rsp+90h] [rbp-70h] BYREF
  IRecordInfo *v22; // [rsp+A0h] [rbp-60h]
  __int128 v23; // [rsp+B0h] [rbp-50h] BYREF
  IRecordInfo *v24; // [rsp+C0h] [rbp-40h]
  __int128 v25; // [rsp+D0h] [rbp-30h] BYREF
  IRecordInfo *v26; // [rsp+E0h] [rbp-20h]
  VARIANTARG v27; // [rsp+F0h] [rbp-10h] BYREF

  v2 = 0;
  if ( !*((_BYTE *)ppv + 16) )
  {
    Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
    v2 = Instance;
    if ( Instance >= 0 )
    {
      v4 = *ppv;
      v5 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)*ppv + 80LL);
      VariantInit(&pvarg);
      v6 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v19);
      v8 = *(_OWORD *)&v19.vt;
      v9 = v19.pRecInfo;
      VariantInit(&v18);
      v10 = *(_OWORD *)&v18.vt;
      v11 = v18.pRecInfo;
      VariantInit(&v17);
      v21 = v6;
      v22 = pRecInfo;
      v23 = v8;
      v24 = v9;
      v25 = v10;
      v26 = v11;
      v27 = v17;
      v2 = v5(v4, &v27, &v25, &v23, &v21);
      v12 = VariantClear(&v17);
      if ( v12 < 0 )
        _com_issue_error(v12);
      v13 = VariantClear(&v18);
      if ( v13 < 0 )
        _com_issue_error(v13);
      v14 = VariantClear(&v19);
      if ( v14 < 0 )
        _com_issue_error(v14);
      v15 = VariantClear(&pvarg);
      if ( v15 < 0 )
        _com_issue_error(v15);
      if ( v2 >= 0 )
        *((_BYTE *)ppv + 16) = 1;
      else
        LogLevelW(2u, L"Error when connecting to Task Scheduler. hr=0x%08x", (unsigned int)v2);
    }
    else
    {
      LogLevelW(2u, L"Unable to CoCreateInstance for Task Scheduler. hr=0x%08x", (unsigned int)Instance);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002fffc  mov     rax, rsp
0x18002ffff  push    rbp
0x180030000  push    rbx
0x180030001  push    rsi
0x180030002  push    rdi
0x180030003  lea     rbp, [rsp-78h]
0x180030008  sub     rsp, 178h
0x18003000f  movaps  xmmword ptr [rax-38h], xmm6
0x180030013  movaps  xmmword ptr [rax-48h], xmm7
0x180030017  movaps  xmmword ptr [rax-58h], xmm8
0x18003001c  movaps  xmmword ptr [rax-68h], xmm9
0x180030021  movaps  xmmword ptr [rax-78h], xmm10
0x180030026  movaps  xmmword ptr [rax-88h], xmm11
0x18003002e  mov     rsi, rcx
0x180030031  xor     ebx, ebx
0x180030033  cmp     [rcx+10h], bl
0x180030036  jnz     loc_180030189
0x18003003c  mov     [rsp+190h+ppv], rcx; ppv
0x180030041  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180030048  xor     edx, edx; pUnkOuter
0x18003004a  lea     r8d, [rbx+1]; dwClsContext
0x18003004e  lea     rcx, CLSID_TaskScheduler; rclsid
0x180030055  call    cs:__imp_CoCreateInstance
0x18003005b  mov     ebx, eax
0x18003005d  test    eax, eax
0x18003005f  jns     short loc_18003007A
0x180030061  mov     r8d, eax
0x180030064  lea     rdx, aUnableToCocrea; "Unable to CoCreateInstance for Task Sch"...
0x18003006b  mov     ecx, 2; unsigned __int8
0x180030070  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180030075  jmp     loc_180030189
0x18003007a  mov     rdi, [rsi]
0x18003007d  mov     rax, [rdi]
0x180030080  mov     rbx, [rax+50h]
0x180030084  lea     rcx, [rsp+190h+pvarg]; pvarg
0x180030089  call    cs:__imp_VariantInit
0x18003008f  nop
0x180030090  movups  xmm10, xmmword ptr [rsp+190h+pvarg]
0x180030096  movsd   xmm11, qword ptr [rbp+90h+pvarg+10h]
0x18003009c  lea     rcx, [rsp+190h+var_130]; pvarg
0x1800300a1  call    cs:__imp_VariantInit
0x1800300a7  nop
0x1800300a8  movups  xmm8, xmmword ptr [rsp+190h+var_130]
0x1800300ae  movsd   xmm9, qword ptr [rsp+190h+var_130+10h]
0x1800300b5  lea     rcx, [rsp+190h+var_148]; pvarg
0x1800300ba  call    cs:__imp_VariantInit
0x1800300c0  nop
0x1800300c1  movups  xmm6, xmmword ptr [rsp+190h+var_148]
0x1800300c6  movsd   xmm7, qword ptr [rsp+190h+var_148+10h]
0x1800300cc  lea     rcx, [rsp+190h+var_160]; pvarg
0x1800300d1  call    cs:__imp_VariantInit
0x1800300d7  nop
0x1800300d8  movups  xmm0, xmmword ptr [rsp+190h+var_160]
0x1800300dd  movsd   xmm1, qword ptr [rsp+190h+var_160+10h]
0x1800300e3  movaps  [rbp+90h+var_100], xmm10
0x1800300e8  movsd   [rbp+90h+var_F0], xmm11
0x1800300ee  movaps  [rbp+90h+var_E0], xmm8
0x1800300f3  movsd   [rbp+90h+var_D0], xmm9
0x1800300f9  movaps  [rbp+90h+var_C0], xmm6
0x1800300fd  movsd   [rbp+90h+var_B0], xmm7
0x180030102  movaps  [rbp+90h+var_A0], xmm0
0x180030106  movsd   [rbp+90h+var_90], xmm1
0x18003010b  lea     rax, [rbp+90h+var_100]
0x18003010f  mov     [rsp+190h+ppv], rax
0x180030114  lea     r9, [rbp+90h+var_E0]
0x180030118  lea     r8, [rbp+90h+var_C0]
0x18003011c  lea     rdx, [rbp+90h+var_A0]
0x180030120  mov     rcx, rdi
0x180030123  mov     rax, rbx
0x180030126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003012b  mov     ebx, eax
0x18003012d  lea     rcx, [rsp+190h+var_160]; pvarg
0x180030132  call    cs:__imp_VariantClear
0x180030138  test    eax, eax
0x18003013a  js      loc_1800301C1
0x180030140  lea     rcx, [rsp+190h+var_148]; pvarg
0x180030145  call    cs:__imp_VariantClear
0x18003014b  test    eax, eax
0x18003014d  js      short loc_1800301C9
0x18003014f  lea     rcx, [rsp+190h+var_130]; pvarg
0x180030154  call    cs:__imp_VariantClear
0x18003015a  test    eax, eax
0x18003015c  js      short loc_1800301D1
0x18003015e  lea     rcx, [rsp+190h+pvarg]; pvarg
0x180030163  call    cs:__imp_VariantClear
0x180030169  test    eax, eax
0x18003016b  js      short loc_1800301B9
0x18003016d  mov     eax, ebx
0x18003016f  shr     eax, 1Fh
0x180030172  test    al, al
0x180030174  jz      short loc_180030185
0x180030176  mov     r8d, ebx
0x180030179  lea     rdx, aErrorWhenConne; "Error when connecting to Task Scheduler"...
0x180030180  jmp     loc_18003006B
0x180030185  mov     byte ptr [rsi+10h], 1
0x180030189  mov     eax, ebx
0x18003018b  lea     r11, [rsp+190h+var_18]
0x180030193  movaps  xmm6, xmmword ptr [r11-18h]
0x180030198  movaps  xmm7, xmmword ptr [r11-28h]
0x18003019d  movaps  xmm8, xmmword ptr [r11-38h]
0x1800301a2  movaps  xmm9, xmmword ptr [r11-48h]
0x1800301a7  movaps  xmm10, xmmword ptr [r11-58h]
0x1800301ac  movaps  xmm11, xmmword ptr [r11-68h]
0x1800301b1  mov     rsp, r11
0x1800301b4  pop     rdi
0x1800301b5  pop     rsi
0x1800301b6  pop     rbx
0x1800301b7  pop     rbp
0x1800301b8  retn
0x1800301b9  mov     ecx, eax; int
0x1800301bb  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800301c1  mov     ecx, eax; int
0x1800301c3  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800301c9  mov     ecx, eax; int
0x1800301cb  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800301d1  mov     ecx, eax; int
0x1800301d3  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
