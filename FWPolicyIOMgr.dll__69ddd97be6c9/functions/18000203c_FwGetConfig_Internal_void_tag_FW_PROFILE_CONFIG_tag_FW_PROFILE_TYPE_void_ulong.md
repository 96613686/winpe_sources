# FwGetConfig_Internal(void *,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,void *,ulong *)

- ea: `0x18000203c`
- end: `0x1800022a7`
- name: `?FwGetConfig_Internal@@YAJPEAXW4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@0PEAK@Z`
- size: `619`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180002c50`

## callees

- `0x180001cdc`
- `0x18000203c`
- `0x1800022b0`
- `0x180004958`
- `0x18001f650`
- `0x18003b010`

## import_xrefs

- `fwbase!FwRegCloseKey` at `0x18000210a`
- `fwbase!FwRegCloseKey` at `0x18000210a`

## string_xrefs

- `0x180002130`: `ProcessConfigParams`
- `0x18000226b`: `ProcessConfigParams`

## pseudocode

```c
__int64 __fastcall FwGetConfig_Internal(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  int v5; // esi
  unsigned int v8; // r12d
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // rdi
  int v12; // eax
  LPCOLESTR v14; // rcx
  unsigned int v15; // esi
  unsigned int v16; // [rsp+40h] [rbp-28h]
  __int64 v17; // [rsp+48h] [rbp-20h] BYREF
  __int64 v18; // [rsp+50h] [rbp-18h] BYREF

  v5 = *(_DWORD *)(a1 + 8);
  v16 = a3;
  v18 = 0;
  v8 = a2;
  v17 = 0;
  v9 = ProcessConfigParams(a1, a2, a3, 1, 0, &v18, &v17, 0);
  if ( v9 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
    {
      v15 = v16;
      goto LABEL_27;
    }
    WPP_SF_ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      123,
      (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      v9,
      (__int64)"ProcessConfigParams");
    v11 = v17;
LABEL_11:
    v15 = v16;
LABEL_12:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_13;
  }
  v11 = v17;
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(v17 + 24))(v18, *(_QWORD *)(v17 + 16), a4, a5);
  v9 = v12;
  if ( v12 != -2147024894 )
  {
    if ( v12 >= 0 )
      goto LABEL_4;
    goto LABEL_11;
  }
  if ( v5 == 1 || v5 == 11 )
    goto LABEL_11;
  v15 = v16;
  v9 = ProcessConfigParams(a1, v8, v16, 1, 0, &v18, &v17, 1);
  if ( v9 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        124,
        (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
        v9,
        (__int64)"ProcessConfigParams");
      v11 = v17;
      goto LABEL_12;
    }
LABEL_27:
    v11 = v17;
    goto LABEL_13;
  }
  v11 = v17;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(v17 + 24))(v18, *(_QWORD *)(v17 + 16), a4, a5);
  if ( v9 >= 0 )
    goto LABEL_4;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
    goto LABEL_4;
  if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      125,
      (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      v9,
      (__int64)"GetFunction");
    goto LABEL_12;
  }
LABEL_13:
  if ( v14 != (LPCOLESTR)&WPP_GLOBAL_Control && (v14[14] & 1) != 0 )
    WPP_SF_ddd(*((_QWORD *)v14 + 2), 126, v10, v8, v15, v9);
LABEL_4:
  if ( v11 && *(_QWORD *)(v11 + 8) )
    FwRegCloseKey(v18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000203c  push    rbp
0x18000203e  push    rbx
0x18000203f  push    rsi
0x180002040  push    rdi
0x180002041  push    r12
0x180002043  push    r13
0x180002045  push    r14
0x180002047  push    r15
0x180002049  mov     rbp, rsp
0x18000204c  sub     rsp, 68h
0x180002050  mov     rax, cs:__security_cookie
0x180002057  xor     rax, rsp
0x18000205a  mov     [rbp+var_10], rax
0x18000205e  mov     esi, [rcx+8]
0x180002061  xor     edi, edi
0x180002063  mov     r15, [rbp+arg_20]
0x180002067  mov     r13, rcx
0x18000206a  mov     [rsp+68h+var_30], edi
0x18000206e  lea     rcx, [rbp+var_20]
0x180002072  mov     [rsp+68h+var_38], rcx
0x180002077  mov     r14, r9
0x18000207a  lea     rcx, [rbp+var_18]
0x18000207e  mov     [rbp+var_28], r8d
0x180002082  mov     [rsp+68h+var_40], rcx
0x180002087  lea     r9d, [rdi+1]
0x18000208b  mov     rcx, r13
0x18000208e  mov     [rbp+var_18], rdi
0x180002092  mov     r12d, edx
0x180002095  mov     [rbp+var_20], rdi
0x180002099  mov     dword ptr [rsp+68h+var_48], edi
0x18000209d  call    ?ProcessConfigParams@@YAJPEAXKW4_tag_FW_PROFILE_TYPE@@KHPEAPEAUHKEY__@@PEAPEAU_tag_WF_CONFIG_DESCRIPTOR@@H@Z; ProcessConfigParams(void *,ulong,_tag_FW_PROFILE_TYPE,ulong,int,HKEY__ * *,_tag_WF_CONFIG_DESCRIPTOR * *,int)
0x1800020a2  mov     ebx, eax
0x1800020a4  lea     rax, WPP_GLOBAL_Control
0x1800020ab  test    ebx, ebx
0x1800020ad  js      short loc_180002112
0x1800020af  mov     rdi, [rbp+var_20]
0x1800020b3  mov     r9, r15
0x1800020b6  mov     rcx, [rbp+var_18]
0x1800020ba  mov     r8, r14
0x1800020bd  mov     rdx, [rdi+10h]
0x1800020c1  mov     rax, [rdi+18h]
0x1800020c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ca  mov     ebx, eax
0x1800020cc  cmp     eax, 80070002h
0x1800020d1  jz      loc_180002196
0x1800020d7  test    eax, eax
0x1800020d9  js      short loc_180002154
0x1800020db  test    rdi, rdi
0x1800020de  jnz     short loc_1800020FF
0x1800020e0  mov     eax, ebx
0x1800020e2  mov     rcx, [rbp+var_10]
0x1800020e6  xor     rcx, rsp; StackCookie
0x1800020e9  call    __security_check_cookie
0x1800020ee  add     rsp, 68h
0x1800020f2  pop     r15
0x1800020f4  pop     r14
0x1800020f6  pop     r13
0x1800020f8  pop     r12
0x1800020fa  pop     rdi
0x1800020fb  pop     rsi
0x1800020fc  pop     rbx
0x1800020fd  pop     rbp
0x1800020fe  retn
0x1800020ff  cmp     qword ptr [rdi+8], 0
0x180002104  jz      short loc_1800020E0
0x180002106  mov     rcx, [rbp+var_18]
0x18000210a  call    cs:__imp_FwRegCloseKey
0x180002110  jmp     short loc_1800020E0
0x180002112  mov     rcx, cs:WPP_GLOBAL_Control
0x180002119  cmp     rcx, rax
0x18000211c  jz      loc_180002294
0x180002122  test    byte ptr [rcx+1Ch], 1
0x180002126  jz      loc_180002294
0x18000212c  mov     rcx, [rcx+10h]
0x180002130  lea     rax, aProcessconfigp; "ProcessConfigParams"
0x180002137  mov     edx, 7Bh ; '{'
0x18000213c  mov     [rsp+68h+var_48], rax
0x180002141  mov     r9d, ebx
0x180002144  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18000214b  call    WPP_SF_ds
0x180002150  mov     rdi, [rbp+var_20]
0x180002154  mov     esi, [rbp+var_28]
0x180002157  lea     r14, WPP_GLOBAL_Control
0x18000215e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002165  cmp     rcx, r14
0x180002168  jz      loc_1800020DB
0x18000216e  test    byte ptr [rcx+1Ch], 1
0x180002172  jz      loc_1800020DB
0x180002178  mov     rcx, [rcx+10h]
0x18000217c  mov     edx, 7Eh ; '~'
0x180002181  mov     dword ptr [rsp+68h+var_40], ebx
0x180002185  mov     r9d, r12d
0x180002188  mov     dword ptr [rsp+68h+var_48], esi
0x18000218c  call    WPP_SF_ddd
0x180002191  jmp     loc_1800020DB
0x180002196  cmp     esi, 1
0x180002199  jz      short loc_180002154
0x18000219b  cmp     esi, 0Bh
0x18000219e  jz      short loc_180002154
0x1800021a0  mov     esi, [rbp+var_28]
0x1800021a3  lea     rax, [rbp+var_20]
0x1800021a7  mov     [rsp+68h+var_30], 1
0x1800021af  mov     r9d, 1
0x1800021b5  mov     [rsp+68h+var_38], rax
0x1800021ba  mov     r8d, esi
0x1800021bd  lea     rax, [rbp+var_18]
0x1800021c1  mov     edx, r12d
0x1800021c4  mov     [rsp+68h+var_40], rax
0x1800021c9  mov     rcx, r13
0x1800021cc  mov     dword ptr [rsp+68h+var_48], 0
0x1800021d4  call    ?ProcessConfigParams@@YAJPEAXKW4_tag_FW_PROFILE_TYPE@@KHPEAPEAUHKEY__@@PEAPEAU_tag_WF_CONFIG_DESCRIPTOR@@H@Z; ProcessConfigParams(void *,ulong,_tag_FW_PROFILE_TYPE,ulong,int,HKEY__ * *,_tag_WF_CONFIG_DESCRIPTOR * *,int)
0x1800021d9  mov     ebx, eax
0x1800021db  test    eax, eax
0x1800021dd  js      short loc_18000224E
0x1800021df  mov     rdi, [rbp+var_20]
0x1800021e3  mov     r9, r15
0x1800021e6  mov     rcx, [rbp+var_18]
0x1800021ea  mov     r8, r14
0x1800021ed  mov     rdx, [rdi+10h]
0x1800021f1  mov     rax, [rdi+18h]
0x1800021f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021fa  mov     ebx, eax
0x1800021fc  test    eax, eax
0x1800021fe  jns     loc_1800020DB
0x180002204  mov     rcx, cs:WPP_GLOBAL_Control
0x18000220b  lea     r14, WPP_GLOBAL_Control
0x180002212  cmp     rcx, r14
0x180002215  jz      loc_1800020DB
0x18000221b  test    byte ptr [rcx+1Ch], 1
0x18000221f  jz      loc_180002165
0x180002225  mov     rcx, [rcx+10h]
0x180002229  lea     rax, aGetfunction; "GetFunction"
0x180002230  mov     edx, 7Dh ; '}'
0x180002235  mov     [rsp+68h+var_48], rax
0x18000223a  mov     r9d, ebx
0x18000223d  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180002244  call    WPP_SF_ds
0x180002249  jmp     loc_18000215E
0x18000224e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002255  lea     r14, WPP_GLOBAL_Control
0x18000225c  cmp     rcx, r14
0x18000225f  jz      short loc_18000229E
0x180002261  test    byte ptr [rcx+1Ch], 1
0x180002265  jz      short loc_18000229E
0x180002267  mov     rcx, [rcx+10h]
0x18000226b  lea     rax, aProcessconfigp; "ProcessConfigParams"
0x180002272  mov     edx, 7Ch ; '|'
0x180002277  mov     [rsp+68h+var_48], rax
0x18000227c  mov     r9d, ebx
0x18000227f  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180002286  call    WPP_SF_ds
0x18000228b  mov     rdi, [rbp+var_20]
0x18000228f  jmp     loc_18000215E
0x180002294  mov     esi, [rbp+var_28]
0x180002297  lea     r14, WPP_GLOBAL_Control
0x18000229e  mov     rdi, [rbp+var_20]
0x1800022a2  jmp     loc_180002165
```
