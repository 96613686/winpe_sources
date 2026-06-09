# KerbClientComputeTgsChecksum(KERB_KDC_REQUEST_BODY *,_KERB_ENCRYPTION_KEY *,ulong,KERB_CHECKSUM *)

- ea: `0x180001c10`
- end: `0x180001e93`
- name: `?KerbClientComputeTgsChecksum@@YAJPEAUKERB_KDC_REQUEST_BODY@@PEAU_KERB_ENCRYPTION_KEY@@KPEAUKERB_CHECKSUM@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(struct KERB_KDC_REQUEST_BODY *, struct _KERB_ENCRYPTION_KEY *, unsigned int, struct KERB_CHECKSUM *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c10`
- `0x180001ea0`
- `0x180007e10`
- `0x180015c10`
- `0x1800160fc`
- `0x180029010`

## import_xrefs

- `cryptdll!CDLocateCheckSum` at `0x180001c56`
- `cryptdll!CDLocateCheckSum` at `0x180001c56`

## string_xrefs

- `0x180001c7f`: `KerbClientComputeTgsChecksum`
- `0x180001e11`: `KerbClientComputeTgsChecksum`

## pseudocode

```c
__int64 __fastcall KerbClientComputeTgsChecksum(
        struct KERB_KDC_REQUEST_BODY *a1,
        struct _KERB_ENCRYPTION_KEY *a2,
        unsigned int a3,
        struct KERB_CHECKSUM *a4)
{
  int v8; // ebx
  _QWORD *v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 (__fastcall *v12)(_QWORD, _QWORD, _QWORD, __int64, __int64 *); // rax
  int v13; // eax
  __int64 (__fastcall *v14)(_QWORD, _QWORD, __int64, __int64 *); // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 (__fastcall *v17)(_QWORD, __int64 *); // rax
  __int64 v19; // [rsp+30h] [rbp-38h] BYREF
  __int64 v20; // [rsp+38h] [rbp-30h] BYREF
  void *v21[2]; // [rsp+40h] [rbp-28h] BYREF

  v19 = 0;
  v20 = 0;
  *(_OWORD *)a4 = 0;
  *((_QWORD *)a4 + 2) = 0;
  *(_OWORD *)v21 = 0;
  v8 = CDLocateCheckSum(a3, &v19);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_336b5a7043973d8457aace61211553a6_Traceguids,
        (unsigned int)"KerbClientComputeTgsChecksum",
        a3,
        v8);
    v9 = (_QWORD *)((char *)a4 + 16);
    goto LABEL_29;
  }
  v10 = ((__int64 (__fastcall *)(_QWORD))qword_1800334A0)(*(unsigned int *)(v19 + 4));
  *((_QWORD *)a4 + 2) = v10;
  v9 = (_QWORD *)((char *)a4 + 16);
  if ( !v10 )
  {
    v8 = -1073741670;
    goto LABEL_29;
  }
  v11 = v19;
  *((_DWORD *)a4 + 2) = *(_DWORD *)(v19 + 4);
  *(_DWORD *)a4 = a3;
  if ( a3 != -132 && a3 != 1 )
  {
    v12 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64 *))(v11 + 56);
    if ( v12 )
    {
      v13 = v12(*((_QWORD *)a2 + 3), *((unsigned int *)a2 + 4), 0, 6, &v20);
      goto LABEL_19;
    }
    v14 = *(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(v19 + 48);
    if ( v14 )
    {
      v13 = v14(*((_QWORD *)a2 + 3), *((unsigned int *)a2 + 4), 6, &v20);
      goto LABEL_19;
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_28:
      v8 = -1073741069;
      goto LABEL_29;
    }
    v16 = 20;
LABEL_27:
    WPP_SF_s(v15[2], v16, WPP_336b5a7043973d8457aace61211553a6_Traceguids, "KerbClientComputeTgsChecksum");
    goto LABEL_28;
  }
  v17 = *(__int64 (__fastcall **)(_QWORD, __int64 *))(v19 + 16);
  if ( !v17 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_28;
    v16 = 19;
    goto LABEL_27;
  }
  v13 = v17(0, &v20);
LABEL_19:
  v8 = v13;
  if ( v13 >= 0 )
  {
    if ( (unsigned int)KerbPackData((__int64)a1, 0x48u, v21, &v21[1]) )
    {
      v8 = -1073741670;
    }
    else
    {
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, void *))(v19 + 24))(v20, LODWORD(v21[0]), v21[1]);
      if ( v8 >= 0 )
        (*(void (__fastcall **)(__int64, _QWORD))(v19 + 32))(v20, *v9);
    }
  }
LABEL_29:
  if ( v20 && v19 )
    (*(void (__fastcall **)(__int64 *))(v19 + 40))(&v20);
  if ( v21[1] )
    MIDL_user_free(v21[1]);
  if ( v8 < 0 && *v9 )
  {
    ((void (*)(void))qword_1800334A8)();
    *(_OWORD *)((char *)a4 + 8) = 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180001c10  mov     r11, rsp
0x180001c13  push    rbx
0x180001c14  push    rsi
0x180001c15  push    rdi
0x180001c16  sub     rsp, 50h
0x180001c1a  mov     [r11+8], rbp
0x180001c1e  xor     eax, eax
0x180001c20  mov     [r11+10h], r14
0x180001c24  xorps   xmm1, xmm1
0x180001c27  mov     [r11+18h], r15
0x180001c2b  mov     r14, rdx
0x180001c2e  mov     r15, rcx
0x180001c31  mov     [r11-38h], rax
0x180001c35  xorps   xmm0, xmm0
0x180001c38  mov     [r11-30h], rax
0x180001c3c  movups  xmmword ptr [r9], xmm1
0x180001c40  mov     ecx, r8d
0x180001c43  mov     [r9+10h], rax
0x180001c47  lea     rdx, [r11-38h]
0x180001c4b  mov     rdi, r9
0x180001c4e  mov     ebp, r8d
0x180001c51  movups  xmmword ptr [rsp+68h+var_28], xmm0
0x180001c56  call    cs:__imp_CDLocateCheckSum
0x180001c5c  mov     ebx, eax
0x180001c5e  test    eax, eax
0x180001c60  jns     short loc_180001CA8
0x180001c62  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c69  lea     rax, WPP_GLOBAL_Control
0x180001c70  cmp     rcx, rax
0x180001c73  jz      short loc_180001C9F
0x180001c75  test    byte ptr [rcx+1Ch], 1
0x180001c79  jz      short loc_180001C9F
0x180001c7b  mov     rcx, [rcx+10h]
0x180001c7f  lea     r9, aKerbclientcomp_0; "KerbClientComputeTgsChecksum"
0x180001c86  mov     edx, 12h
0x180001c8b  mov     [rsp+68h+var_40], ebx
0x180001c8f  lea     r8, WPP_336b5a7043973d8457aace61211553a6_Traceguids
0x180001c96  mov     dword ptr [rsp+68h+var_48], ebp
0x180001c9a  call    WPP_SF_sdD
0x180001c9f  lea     rsi, [rdi+10h]
0x180001ca3  jmp     loc_180001E29
0x180001ca8  mov     rcx, [rsp+68h+var_38]
0x180001cad  mov     rax, cs:qword_1800334A0
0x180001cb4  mov     ecx, [rcx+4]
0x180001cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cbc  mov     [rdi+10h], rax
0x180001cc0  lea     rsi, [rdi+10h]
0x180001cc4  test    rax, rax
0x180001cc7  jnz     short loc_180001CD3
0x180001cc9  mov     ebx, 0C000009Ah
0x180001cce  jmp     loc_180001E29
0x180001cd3  mov     rdx, [rsp+68h+var_38]
0x180001cd8  mov     eax, [rdx+4]
0x180001cdb  mov     [rdi+8], eax
0x180001cde  mov     [rdi], ebp
0x180001ce0  cmp     ebp, 0FFFFFF7Ch
0x180001ce6  jz      loc_180001D6F
0x180001cec  cmp     ebp, 1
0x180001cef  jz      short loc_180001D6F
0x180001cf1  mov     rax, [rdx+38h]
0x180001cf5  test    rax, rax
0x180001cf8  jz      short loc_180001D1C
0x180001cfa  mov     edx, [r14+10h]
0x180001cfe  lea     rcx, [rsp+68h+var_30]
0x180001d03  mov     [rsp+68h+var_48], rcx
0x180001d08  mov     r9d, 6
0x180001d0e  mov     rcx, [r14+18h]
0x180001d12  xor     r8d, r8d
0x180001d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d1a  jmp     short loc_180001D89
0x180001d1c  mov     rax, [rsp+68h+var_38]
0x180001d21  mov     rax, [rax+30h]
0x180001d25  test    rax, rax
0x180001d28  jz      short loc_180001D44
0x180001d2a  mov     edx, [r14+10h]
0x180001d2e  lea     r9, [rsp+68h+var_30]
0x180001d33  mov     rcx, [r14+18h]
0x180001d37  mov     r8d, 6
0x180001d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d42  jmp     short loc_180001D89
0x180001d44  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d4b  lea     rax, WPP_GLOBAL_Control
0x180001d52  cmp     rcx, rax
0x180001d55  jz      loc_180001E24
0x180001d5b  test    byte ptr [rcx+1Ch], 1
0x180001d5f  jz      loc_180001E24
0x180001d65  mov     edx, 14h
0x180001d6a  jmp     loc_180001E0D
0x180001d6f  mov     rax, [rsp+68h+var_38]
0x180001d74  mov     rax, [rax+10h]
0x180001d78  test    rax, rax
0x180001d7b  jz      short loc_180001DEF
0x180001d7d  lea     rdx, [rsp+68h+var_30]
0x180001d82  xor     ecx, ecx
0x180001d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d89  mov     ebx, eax
0x180001d8b  test    eax, eax
0x180001d8d  js      loc_180001E29
0x180001d93  lea     r9, [rsp+68h+var_28+8]
0x180001d98  mov     edx, 48h ; 'H'
0x180001d9d  lea     r8, [rsp+68h+var_28]
0x180001da2  mov     rcx, r15
0x180001da5  call    KerbPackData
0x180001daa  test    eax, eax
0x180001dac  jz      short loc_180001DB5
0x180001dae  mov     ebx, 0C000009Ah
0x180001db3  jmp     short loc_180001E29
0x180001db5  mov     rax, [rsp+68h+var_38]
0x180001dba  mov     r8, [rsp+68h+var_28+8]
0x180001dbf  mov     edx, dword ptr [rsp+68h+var_28]
0x180001dc3  mov     rcx, [rsp+68h+var_30]
0x180001dc8  mov     rax, [rax+18h]
0x180001dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dd1  mov     ebx, eax
0x180001dd3  test    eax, eax
0x180001dd5  js      short loc_180001E29
0x180001dd7  mov     rax, [rsp+68h+var_38]
0x180001ddc  mov     rdx, [rsi]
0x180001ddf  mov     rcx, [rsp+68h+var_30]
0x180001de4  mov     rax, [rax+20h]
0x180001de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ded  jmp     short loc_180001E29
0x180001def  mov     rcx, cs:WPP_GLOBAL_Control
0x180001df6  lea     rax, WPP_GLOBAL_Control
0x180001dfd  cmp     rcx, rax
0x180001e00  jz      short loc_180001E24
0x180001e02  test    byte ptr [rcx+1Ch], 1
0x180001e06  jz      short loc_180001E24
0x180001e08  mov     edx, 13h
0x180001e0d  mov     rcx, [rcx+10h]
0x180001e11  lea     r9, aKerbclientcomp_0; "KerbClientComputeTgsChecksum"
0x180001e18  lea     r8, WPP_336b5a7043973d8457aace61211553a6_Traceguids
0x180001e1f  call    WPP_SF_s
0x180001e24  mov     ebx, 0C00002F3h
0x180001e29  cmp     [rsp+68h+var_30], 0
0x180001e2f  mov     r15, [rsp+68h+arg_10]
0x180001e37  mov     r14, [rsp+68h+arg_8]
0x180001e3c  mov     rbp, [rsp+68h+arg_0]
0x180001e41  jz      short loc_180001E5B
0x180001e43  mov     rdx, [rsp+68h+var_38]
0x180001e48  test    rdx, rdx
0x180001e4b  jz      short loc_180001E5B
0x180001e4d  mov     rax, [rdx+28h]
0x180001e51  lea     rcx, [rsp+68h+var_30]
0x180001e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e5b  mov     rcx, [rsp+68h+var_28+8]; void *
0x180001e60  test    rcx, rcx
0x180001e63  jz      short loc_180001E6A
0x180001e65  call    MIDL_user_free
0x180001e6a  test    ebx, ebx
0x180001e6c  jns     short loc_180001E89
0x180001e6e  mov     rcx, [rsi]
0x180001e71  test    rcx, rcx
0x180001e74  jz      short loc_180001E89
0x180001e76  mov     rax, cs:qword_1800334A8
0x180001e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e82  xorps   xmm0, xmm0
0x180001e85  movups  xmmword ptr [rdi+8], xmm0
0x180001e89  mov     eax, ebx
0x180001e8b  add     rsp, 50h
0x180001e8f  pop     rdi
0x180001e90  pop     rsi
0x180001e91  pop     rbx
0x180001e92  retn
```
