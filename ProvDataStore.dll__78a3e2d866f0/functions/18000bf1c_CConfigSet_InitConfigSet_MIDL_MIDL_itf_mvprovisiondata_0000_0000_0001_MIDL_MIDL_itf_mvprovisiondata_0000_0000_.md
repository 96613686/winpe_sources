# CConfigSet::InitConfigSet(__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0001,__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0002,IMVKey * *,ulong,OperatorKeys,ushort const *,__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0003,ulong,ulong,ulong,int,bool)

- ea: `0x18000bf1c`
- end: `0x18000c067`
- name: `?InitConfigSet@CConfigSet@@QEAAJW4__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0001@@W4__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0002@@PEAPEAUIMVKey@@KW4OperatorKeys@@PEBGW4__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0003@@KKKH_N@Z`
- size: `331`
- prototype: `__int64 __fastcall(__int64, int, int, _QWORD **, int, int, unsigned __int16 *, int, int, unsigned int, int, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e184`

## callees

- `0x180006d94`
- `0x18000bf1c`
- `0x18000fa60`
- `0x180010f80`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c037`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c037`

## pseudocode

```c
__int64 __fastcall CConfigSet::InitConfigSet(
        __int64 a1,
        int a2,
        int a3,
        _QWORD **a4,
        int a5,
        int a6,
        unsigned __int16 *a7,
        int a8,
        int a9,
        unsigned int a10,
        int a11,
        int a12,
        char a13)
{
  int v17; // edi
  __int64 i; // rbp
  unsigned __int16 v20[264]; // [rsp+20h] [rbp-238h] BYREF

  switch ( a3 )
  {
    case 0:
      goto LABEL_7;
    case 1:
LABEL_6:
      *(_DWORD *)(a1 + 32) = a5;
      *(_DWORD *)(a1 + 72) = a8;
      *(_DWORD *)a1 = a2;
      *(_DWORD *)(a1 + 4) = a3;
      *(_DWORD *)(a1 + 76) = a12 != 0 ? 0 : 2;
      v17 = 0;
      *(_DWORD *)(a1 + 104) = a6;
      *(_DWORD *)(a1 + 112) = a10;
      *(_DWORD *)(a1 + 108) = a9;
      *(_DWORD *)(a1 + 116) = a11;
      *(_BYTE *)(a1 + 120) = a13;
      *(_QWORD *)(a1 + 24) = a4;
      return (unsigned int)v17;
    case 2:
      v17 = TranslatePath(a7, v20, 2u);
      if ( v17 >= 0 )
      {
        v17 = CoAllocString(v20, (unsigned __int16 **)(a1 + 8));
        if ( v17 >= 0 )
          goto LABEL_6;
      }
      break;
    default:
LABEL_7:
      v17 = -2147418113;
      break;
  }
  if ( a4 )
  {
    for ( i = 0; (unsigned int)i < a10; i = (unsigned int)(i + 1) )
    {
      (*(void (__fastcall **)(_QWORD *))(*a4[i] + 16LL))(a4[i]);
      a4[i] = 0;
    }
    CoTaskMemFree(a4);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000bf1c  mov     [rsp+arg_8], rbx
0x18000bf21  mov     [rsp+arg_10], rbp
0x18000bf26  push    rsi
0x18000bf27  push    rdi
0x18000bf28  push    r14
0x18000bf2a  sub     rsp, 240h
0x18000bf31  mov     rax, cs:__security_cookie
0x18000bf38  xor     rax, rsp
0x18000bf3b  mov     [rsp+258h+var_28], rax
0x18000bf43  mov     rsi, r9
0x18000bf46  mov     rbx, rcx
0x18000bf49  mov     rcx, [rsp+258h+arg_30]; unsigned __int16 *
0x18000bf51  mov     r9d, r8d
0x18000bf54  mov     ebp, r8d
0x18000bf57  mov     r14d, edx
0x18000bf5a  test    r8d, r8d
0x18000bf5d  jz      loc_18000BFFC
0x18000bf63  sub     r9d, 1
0x18000bf67  jz      short loc_18000BF97
0x18000bf69  cmp     r9d, 1
0x18000bf6d  jnz     loc_18000BFFC
0x18000bf73  lea     rdx, [rsp+258h+var_238]; unsigned __int16 *
0x18000bf78  call    ?TranslatePath@@YAJPEBGPEAGK@Z; TranslatePath(ushort const *,ushort *,ulong)
0x18000bf7d  mov     edi, eax
0x18000bf7f  test    eax, eax
0x18000bf81  js      short loc_18000C001
0x18000bf83  lea     rdx, [rbx+8]; unsigned __int16 **
0x18000bf87  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x18000bf8c  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18000bf91  mov     edi, eax
0x18000bf93  test    eax, eax
0x18000bf95  js      short loc_18000C001
0x18000bf97  mov     eax, [rsp+258h+arg_20]
0x18000bf9e  neg     [rsp+258h+arg_58]
0x18000bfa5  mov     [rbx+20h], eax
0x18000bfa8  mov     eax, [rsp+258h+arg_38]
0x18000bfaf  mov     [rbx+48h], eax
0x18000bfb2  sbb     eax, eax
0x18000bfb4  not     eax
0x18000bfb6  mov     [rbx], r14d
0x18000bfb9  and     eax, 2
0x18000bfbc  mov     [rbx+4], ebp
0x18000bfbf  mov     [rbx+4Ch], eax
0x18000bfc2  xor     edi, edi
0x18000bfc4  mov     eax, [rsp+258h+arg_28]
0x18000bfcb  mov     [rbx+68h], eax
0x18000bfce  mov     eax, [rsp+258h+arg_48]
0x18000bfd5  mov     [rbx+70h], eax
0x18000bfd8  mov     eax, [rsp+258h+arg_40]
0x18000bfdf  mov     [rbx+6Ch], eax
0x18000bfe2  mov     eax, [rsp+258h+arg_50]
0x18000bfe9  mov     [rbx+74h], eax
0x18000bfec  mov     al, [rsp+258h+arg_60]
0x18000bff3  mov     [rbx+78h], al
0x18000bff6  mov     [rbx+18h], rsi
0x18000bffa  jmp     short loc_18000C03D
0x18000bffc  mov     edi, 8000FFFFh
0x18000c001  test    rsi, rsi
0x18000c004  jz      short loc_18000C03D
0x18000c006  mov     r14d, [rsp+258h+arg_48]
0x18000c00e  xor     ebp, ebp
0x18000c010  test    r14d, r14d
0x18000c013  jz      short loc_18000C034
0x18000c015  mov     rcx, [rsi+rbp*8]
0x18000c019  mov     rax, [rcx]
0x18000c01c  mov     rax, [rax+10h]
0x18000c020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c025  mov     qword ptr [rsi+rbp*8], 0
0x18000c02d  inc     ebp
0x18000c02f  cmp     ebp, r14d
0x18000c032  jb      short loc_18000C015
0x18000c034  mov     rcx, rsi; pv
0x18000c037  call    cs:__imp_CoTaskMemFree
0x18000c03d  mov     eax, edi
0x18000c03f  mov     rcx, [rsp+258h+var_28]
0x18000c047  xor     rcx, rsp; StackCookie
0x18000c04a  call    __security_check_cookie
0x18000c04f  lea     r11, [rsp+258h+var_18]
0x18000c057  mov     rbx, [r11+28h]
0x18000c05b  mov     rbp, [r11+30h]
0x18000c05f  mov     rsp, r11
0x18000c062  pop     r14
0x18000c064  pop     rdi
0x18000c065  pop     rsi
0x18000c066  retn
```
