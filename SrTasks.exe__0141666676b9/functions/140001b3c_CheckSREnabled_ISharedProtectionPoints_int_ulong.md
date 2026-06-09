# CheckSREnabled(ISharedProtectionPoints *,int *,ulong *)

- ea: `0x140001b3c`
- end: `0x140001de6`
- name: `?CheckSREnabled@@YAJPEAUISharedProtectionPoints@@PEAHPEAK@Z`
- size: `682`
- prototype: `__int64 __fastcall(struct ISharedProtectionPoints *, int *, unsigned int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x140002ae8`
- `0x140004a70`
- `0x1400050f0`

## callees

- `0x140001b3c`
- `0x140002e1c`
- `0x140002e44`
- `0x140005784`
- `0x14000d12c`
- `0x14000e324`
- `0x14000e41c`
- `0x140011010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140001dbb`
- `ole32!CoTaskMemFree` at `0x140001dbb`

## pseudocode

```c
__int64 __fastcall CheckSREnabled(struct ISharedProtectionPoints *a1, int *a2, unsigned int *a3)
{
  const unsigned __int16 *v6; // rdx
  unsigned __int16 *v7; // rcx
  __int16 v8; // ax
  int v9; // ebx
  __int16 v10; // ax
  int v11; // r14d
  int v12; // r13d
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r15
  __int64 i; // rbx
  int v18; // [rsp+30h] [rbp-40h] BYREF
  __int16 v19; // [rsp+34h] [rbp-3Ch]
  __int16 v20; // [rsp+36h] [rbp-3Ah]
  unsigned int v21; // [rsp+B0h] [rbp+40h] BYREF
  int v22; // [rsp+B8h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp+50h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_cc2da48973373651002ff2feee037f2e_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "CheckSREnabled", 29, 1);
  v21 = 0;
  pv = 0;
  v22 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v8 = 44;
  if ( a1 && (v19 = 44, v8 = 45, a2) )
  {
    v18 = 0;
    v19 = 45;
    v9 = SxQueryGroupPolicy(v7, v6, &v22);
    v18 = v9;
    v8 = 48;
    if ( v9 >= 0 )
    {
      v19 = 48;
      if ( v22 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_cc2da48973373651002ff2feee037f2e_Traceguids);
        }
        v10 = 52;
        goto LABEL_16;
      }
      v9 = (*(__int64 (__fastcall **)(struct ISharedProtectionPoints *, _QWORD, unsigned int *, LPVOID *))(*(_QWORD *)a1 + 96LL))(
             a1,
             0,
             &v21,
             &pv);
      v18 = v9;
      v8 = 56;
      if ( v9 >= 0 )
      {
        v11 = 0;
        v19 = 56;
        v12 = 0;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_cc2da48973373651002ff2feee037f2e_Traceguids, v21);
          v13 = WPP_GLOBAL_Control;
        }
        v14 = 0;
        if ( v21 )
        {
          while ( 1 )
          {
            v15 = 6 * v14;
            if ( *((_QWORD *)pv + 6 * v14) == 0x4180294E09F7EDC5LL
              && *((_QWORD *)pv + 6 * v14 + 1) == 0x13950E6A0EFB6AAFLL )
            {
              break;
            }
            v14 = (unsigned int)(v14 + 1);
            if ( (unsigned int)v14 >= v21 )
              goto LABEL_31;
          }
          if ( v13 != &WPP_GLOBAL_Control && (*((_DWORD *)v13 + 7) & 0x8000000) != 0 )
            WPP_SF_(v13[2], 13, &WPP_cc2da48973373651002ff2feee037f2e_Traceguids);
          v11 = 1;
          v12 = *((_DWORD *)pv + 2 * v15 + 6);
        }
LABEL_31:
        *a2 = v11;
        if ( a3 )
          *a3 = v12 - 1;
        if ( v11 )
        {
          v9 = 0;
          v10 = 83;
          goto LABEL_17;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_cc2da48973373651002ff2feee037f2e_Traceguids);
        }
        v10 = 87;
LABEL_16:
        v9 = 1;
LABEL_17:
        v18 = v9;
        v19 = v10;
        goto LABEL_41;
      }
    }
  }
  else
  {
    v9 = -2147024809;
    v18 = -2147024809;
  }
  v20 = v8;
LABEL_41:
  if ( pv )
  {
    for ( i = 0; (unsigned int)i < v21; i = (unsigned int)(i + 1) )
      Free_SPP_CLIENT_PROP((struct _SPP_CLIENT_PROP *)((char *)pv + 48 * i));
    CoTaskMemFree(pv);
    v9 = v18;
    pv = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140001b3c  push    rbp
0x140001b3e  push    rbx
0x140001b3f  push    rsi
0x140001b40  push    rdi
0x140001b41  push    r13
0x140001b43  push    r14
0x140001b45  push    r15
0x140001b47  mov     rbp, rsp
0x140001b4a  sub     rsp, 70h
0x140001b4e  mov     rdi, r8
0x140001b51  mov     rsi, rdx
0x140001b54  mov     r14, rcx
0x140001b57  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b5e  lea     r15, WPP_GLOBAL_Control
0x140001b65  cmp     rcx, r15
0x140001b68  jz      short loc_140001B88
0x140001b6a  test    dword ptr [rcx+1Ch], 20000000h
0x140001b71  jz      short loc_140001B88
0x140001b73  mov     rcx, [rcx+10h]
0x140001b77  lea     r8, WPP_cc2da48973373651002ff2feee037f2e_Traceguids
0x140001b7e  mov     edx, 0Ah
0x140001b83  call    WPP_SF_
0x140001b88  mov     r9d, 1; unsigned __int16
0x140001b8e  lea     rdx, aChecksrenabled; "CheckSREnabled"
0x140001b95  lea     rcx, [rbp+var_40]; this
0x140001b99  lea     r8d, [r9+1Ch]; unsigned __int16
0x140001b9d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140001ba2  mov     [rbp+arg_0], 0
0x140001ba9  mov     [rbp+pv], 0
0x140001bb1  mov     [rbp+arg_8], 0
0x140001bb8  test    rsi, rsi
0x140001bbb  jz      short loc_140001BC3
0x140001bbd  mov     dword ptr [rsi], 0
0x140001bc3  test    rdi, rdi
0x140001bc6  jz      short loc_140001BCE
0x140001bc8  mov     dword ptr [rdi], 0
0x140001bce  mov     eax, 2Ch ; ','
0x140001bd3  test    r14, r14
0x140001bd6  jz      loc_140001D85
0x140001bdc  mov     [rbp+var_3C], ax
0x140001be0  mov     eax, 2Dh ; '-'
0x140001be5  test    rsi, rsi
0x140001be8  jz      loc_140001D85
0x140001bee  lea     r8, [rbp+arg_8]; int *
0x140001bf2  mov     [rbp+var_40], 0
0x140001bf9  mov     [rbp+var_3C], ax
0x140001bfd  call    ?SxQueryGroupPolicy@@YAJPEBG0PEAH@Z; SxQueryGroupPolicy(ushort const *,ushort const *,int *)
0x140001c02  mov     ebx, eax
0x140001c04  mov     [rbp+var_40], eax
0x140001c07  test    eax, eax
0x140001c09  mov     eax, 30h ; '0'
0x140001c0e  js      loc_140001D8D
0x140001c14  cmp     [rbp+arg_8], 0
0x140001c18  mov     [rbp+var_3C], ax
0x140001c1c  jz      short loc_140001C5D
0x140001c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c25  cmp     rcx, r15
0x140001c28  jz      short loc_140001C47
0x140001c2a  mov     ebx, 8000000h
0x140001c2f  test    [rcx+1Ch], ebx
0x140001c32  jz      short loc_140001C47
0x140001c34  mov     rcx, [rcx+10h]
0x140001c38  lea     edx, [rax-25h]
0x140001c3b  lea     r8, WPP_cc2da48973373651002ff2feee037f2e_Traceguids
0x140001c42  call    WPP_SF_
0x140001c47  mov     eax, 34h ; '4'
0x140001c4c  mov     ebx, 1
0x140001c51  mov     [rbp+var_40], ebx
0x140001c54  mov     [rbp+var_3C], ax
0x140001c58  jmp     loc_140001D91
0x140001c5d  mov     rax, [r14]
0x140001c60  lea     r9, [rbp+pv]
0x140001c64  lea     r8, [rbp+arg_0]
0x140001c68  xor     edx, edx
0x140001c6a  mov     rcx, r14
0x140001c6d  mov     rax, [rax+60h]
0x140001c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001c76  mov     ebx, eax
0x140001c78  mov     [rbp+var_40], eax
0x140001c7b  test    eax, eax
0x140001c7d  mov     eax, 38h ; '8'
0x140001c82  js      loc_140001D8D
0x140001c88  xor     r14d, r14d
0x140001c8b  mov     [rbp+var_3C], ax
0x140001c8f  xor     r13d, r13d
0x140001c92  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c99  mov     ebx, 8000000h
0x140001c9e  cmp     rcx, r15
0x140001ca1  jz      short loc_140001CC6
0x140001ca3  test    [rcx+1Ch], ebx
0x140001ca6  jz      short loc_140001CC6
0x140001ca8  mov     r9d, [rbp+arg_0]
0x140001cac  lea     edx, [rax-2Ch]
0x140001caf  mov     rcx, [rcx+10h]
0x140001cb3  lea     r8, WPP_cc2da48973373651002ff2feee037f2e_Traceguids
0x140001cba  call    WPP_SF_d
0x140001cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x140001cc6  xor     edx, edx
0x140001cc8  cmp     [rbp+arg_0], edx
0x140001ccb  jbe     short loc_140001D38
0x140001ccd  mov     r8, cs:qword_140012C70
0x140001cd4  mov     r9, cs:qword_140012C68
0x140001cdb  mov     rax, [rbp+pv]
0x140001cdf  lea     r15, [rdx+rdx*2]
0x140001ce3  add     r15, r15
0x140001ce6  cmp     [rax+r15*8], r9
0x140001cea  jnz     short loc_140001CF3
0x140001cec  cmp     [rax+r15*8+8], r8
0x140001cf1  jz      short loc_140001CFC
0x140001cf3  inc     edx
0x140001cf5  cmp     edx, [rbp+arg_0]
0x140001cf8  jb      short loc_140001CDB
0x140001cfa  jmp     short loc_140001D31
0x140001cfc  lea     rax, WPP_GLOBAL_Control
0x140001d03  cmp     rcx, rax
0x140001d06  jz      short loc_140001D22
0x140001d08  test    [rcx+1Ch], ebx
0x140001d0b  jz      short loc_140001D22
0x140001d0d  mov     rcx, [rcx+10h]
0x140001d11  lea     r8, WPP_cc2da48973373651002ff2feee037f2e_Traceguids
0x140001d18  mov     edx, 0Dh
0x140001d1d  call    WPP_SF_
0x140001d22  mov     rax, [rbp+pv]
0x140001d26  mov     r14d, 1
0x140001d2c  mov     r13d, [rax+r15*8+18h]
0x140001d31  lea     r15, WPP_GLOBAL_Control
0x140001d38  mov     [rsi], r14d
0x140001d3b  test    rdi, rdi
0x140001d3e  jz      short loc_140001D46
0x140001d40  lea     eax, [r13-1]
0x140001d44  mov     [rdi], eax
0x140001d46  test    r14d, r14d
0x140001d49  jz      short loc_140001D55
0x140001d4b  xor     ebx, ebx
0x140001d4d  lea     eax, [rbx+53h]
0x140001d50  jmp     loc_140001C51
0x140001d55  mov     rcx, cs:WPP_GLOBAL_Control
0x140001d5c  cmp     rcx, r15
0x140001d5f  jz      short loc_140001D7B
0x140001d61  test    [rcx+1Ch], ebx
0x140001d64  jz      short loc_140001D7B
0x140001d66  mov     rcx, [rcx+10h]
0x140001d6a  lea     r8, WPP_cc2da48973373651002ff2feee037f2e_Traceguids
0x140001d71  mov     edx, 0Eh
0x140001d76  call    WPP_SF_
0x140001d7b  mov     eax, 57h ; 'W'
0x140001d80  jmp     loc_140001C4C
0x140001d85  mov     ebx, 80070057h
0x140001d8a  mov     [rbp+var_40], ebx
0x140001d8d  mov     [rbp+var_3A], ax
0x140001d91  cmp     [rbp+pv], 0
0x140001d96  jz      short loc_140001DCC
0x140001d98  xor     ebx, ebx
0x140001d9a  cmp     [rbp+arg_0], ebx
0x140001d9d  jbe     short loc_140001DB7
0x140001d9f  lea     rcx, [rbx+rbx*2]
0x140001da3  shl     rcx, 4
0x140001da7  add     rcx, [rbp+pv]; struct _SPP_CLIENT_PROP *
0x140001dab  call    ?Free_SPP_CLIENT_PROP@@YAXPEAU_SPP_CLIENT_PROP@@@Z; Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *)
0x140001db0  inc     ebx
0x140001db2  cmp     ebx, [rbp+arg_0]
0x140001db5  jb      short loc_140001D9F
0x140001db7  mov     rcx, [rbp+pv]; pv
0x140001dbb  call    cs:__imp_CoTaskMemFree
0x140001dc1  mov     ebx, [rbp+var_40]
0x140001dc4  mov     [rbp+pv], 0
0x140001dcc  lea     rcx, [rbp+var_40]; this
0x140001dd0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140001dd5  mov     eax, ebx
0x140001dd7  add     rsp, 70h
0x140001ddb  pop     r15
0x140001ddd  pop     r14
0x140001ddf  pop     r13
0x140001de1  pop     rdi
0x140001de2  pop     rsi
0x140001de3  pop     rbx
0x140001de4  pop     rbp
0x140001de5  retn
```
