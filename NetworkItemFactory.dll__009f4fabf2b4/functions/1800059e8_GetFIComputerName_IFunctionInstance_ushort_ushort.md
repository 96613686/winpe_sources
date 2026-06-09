# GetFIComputerName(IFunctionInstance *,ushort * *,ushort * *)

- ea: `0x1800059e8`
- end: `0x180005b7c`
- name: `?GetFIComputerName@@YAJPEAUIFunctionInstance@@PEAPEAG1@Z`
- size: `404`
- prototype: `__int64 __fastcall(struct IFunctionInstance *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002ab8`
- `0x18000433c`

## callees

- `0x1800059e8`
- `0x180005b84`
- `0x180005bec`
- `0x180006008`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005aaf`
- `ole32!CoTaskMemFree` at `0x180005afb`
- `ole32!CoTaskMemFree` at `0x180005b10`
- `ole32!CoTaskMemFree` at `0x180005b1c`
- `ole32!CoTaskMemFree` at `0x180005b5f`
- `ole32!CoTaskMemFree` at `0x180005aaf`
- `ole32!CoTaskMemFree` at `0x180005afb`
- `ole32!CoTaskMemFree` at `0x180005b10`
- `ole32!CoTaskMemFree` at `0x180005b1c`
- `ole32!CoTaskMemFree` at `0x180005b5f`
- `SHLWAPI!SHStrDupW` at `0x180005a9f`
- `SHLWAPI!SHStrDupW` at `0x180005aef`
- `SHLWAPI!SHStrDupW` at `0x180005a9f`
- `SHLWAPI!SHStrDupW` at `0x180005aef`

## pseudocode

```c
__int64 __fastcall GetFIComputerName(struct IFunctionInstance *a1, struct _tagpropertykey *a2, unsigned __int16 **a3)
{
  int v6; // eax
  int FIProperty; // ebx
  const PROPERTYKEY *v8; // rdx
  void *v9; // rcx
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // rax
  HRESULT v12; // eax
  int v13; // edi
  unsigned __int16 *v14; // rcx
  HRESULT v15; // eax
  unsigned __int16 *v17; // [rsp+68h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+50h] BYREF
  unsigned __int16 *v19; // [rsp+78h] [rbp+58h] BYREF

  v6 = 2;
  do
  {
    *a3 = 0;
    *(_QWORD *)&a2->fmtid.Data1 = 0;
    --v6;
  }
  while ( v6 );
  LODWORD(v17) = 0;
  FIProperty = GetFIProperty(a1, a2, (unsigned int *)&v17);
  if ( FIProperty >= 0 )
  {
    if ( (((_DWORD)v17 - 2) & 0xFFFFFFF7) != 0 )
      return (unsigned int)-2147467259;
    pv = 0;
    v8 = &PKEY_ComputerName;
    if ( (_DWORD)v17 != 2 )
      v8 = &PKEY_WNET_RemoteName;
    FIProperty = GetFIProperty(a1, v8, (unsigned __int16 **)&pv);
    if ( FIProperty >= 0 )
    {
      v9 = pv;
      v10 = -1;
      v11 = -1;
      do
        ++v11;
      while ( *((_WORD *)pv + v11) );
      FIProperty = -2147418113;
      if ( v11 <= 2 )
      {
        v13 = -2147418113;
      }
      else
      {
        v12 = SHStrDupW((LPCWSTR)pv + 2, (LPWSTR *)a2);
        v9 = pv;
        v13 = v12;
      }
      CoTaskMemFree(v9);
      if ( v13 < 0 )
      {
        FIProperty = v13;
      }
      else
      {
        v19 = 0;
        if ( GetFIProperty(a1, &PKEY_PNPX_DomainName, &v19) < 0 )
          return (unsigned int)v13;
        v14 = v19;
        do
          ++v10;
        while ( v19[v10] );
        if ( v10 > 2 )
        {
          v15 = SHStrDupW(v19 + 2, a3);
          v14 = v19;
          FIProperty = v15;
        }
        CoTaskMemFree(v14);
        if ( FIProperty >= 0 )
          goto LABEL_25;
      }
    }
    CoTaskMemFree(*(LPVOID *)&a2->fmtid.Data1);
    *(_QWORD *)&a2->fmtid.Data1 = 0;
    CoTaskMemFree(*a3);
    *a3 = 0;
  }
LABEL_25:
  if ( FIProperty == -2147023288 )
  {
    v17 = 0;
    FIProperty = GetFIProperty(a1, &PKEY_PUBSVCS_METADATA, &v17);
    if ( FIProperty >= 0 )
    {
      FIProperty = ParsePubsubString(v17, (unsigned __int16 **)a2, a3);
      CoTaskMemFree(v17);
    }
  }
  return (unsigned int)FIProperty;
}

```

## disassembly

```asm
0x1800059e8  mov     [rsp-38h+arg_0], rbx
0x1800059ed  push    rbp
0x1800059ee  push    rsi
0x1800059ef  push    rdi
0x1800059f0  push    r12
0x1800059f2  push    r13
0x1800059f4  push    r14
0x1800059f6  push    r15
0x1800059f8  mov     rbp, rsp
0x1800059fb  sub     rsp, 20h
0x1800059ff  mov     rsi, r8
0x180005a02  mov     r15, rdx
0x180005a05  mov     r12, rcx
0x180005a08  mov     eax, 2
0x180005a0d  xor     r13d, r13d
0x180005a10  mov     [r8], r13
0x180005a13  mov     [rdx], r13
0x180005a16  sub     eax, 1
0x180005a19  jnz     short loc_180005A10
0x180005a1b  lea     r8, [rbp+arg_8]; unsigned int *
0x180005a1f  mov     dword ptr [rbp+arg_8], r13d
0x180005a23  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAI@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,uint *)
0x180005a28  mov     ebx, eax
0x180005a2a  test    eax, eax
0x180005a2c  js      loc_180005B25
0x180005a32  mov     ecx, dword ptr [rbp+arg_8]
0x180005a35  lea     eax, [rcx-2]
0x180005a38  test    eax, 0FFFFFFF7h
0x180005a3d  jz      short loc_180005A49
0x180005a3f  mov     ebx, 80004005h
0x180005a44  jmp     loc_180005B65
0x180005a49  cmp     ecx, 2
0x180005a4c  mov     [rbp+pv], r13
0x180005a50  lea     rax, PKEY_WNET_RemoteName
0x180005a57  mov     rcx, r12; struct IFunctionInstance *
0x180005a5a  lea     rdx, PKEY_ComputerName
0x180005a61  cmovnz  rdx, rax; struct _tagpropertykey *
0x180005a65  lea     r8, [rbp+pv]; unsigned __int16 **
0x180005a69  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAPEAG@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,ushort * *)
0x180005a6e  mov     ebx, eax
0x180005a70  test    eax, eax
0x180005a72  js      loc_180005B0D
0x180005a78  mov     rcx, [rbp+pv]; pv
0x180005a7c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180005a80  mov     rax, r14
0x180005a83  inc     rax
0x180005a86  cmp     [rcx+rax*2], r13w
0x180005a8b  jnz     short loc_180005A83
0x180005a8d  mov     ebx, 8000FFFFh
0x180005a92  cmp     rax, 2
0x180005a96  jbe     short loc_180005AAD
0x180005a98  add     rcx, 4; psz
0x180005a9c  mov     rdx, r15; ppwsz
0x180005a9f  call    cs:__imp_SHStrDupW
0x180005aa5  mov     rcx, [rbp+pv]
0x180005aa9  mov     edi, eax
0x180005aab  jmp     short loc_180005AAF
0x180005aad  mov     edi, ebx
0x180005aaf  call    cs:__imp_CoTaskMemFree
0x180005ab5  test    edi, edi
0x180005ab7  js      short loc_180005B0B
0x180005ab9  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x180005abd  mov     [rbp+arg_18], r13
0x180005ac1  lea     rdx, PKEY_PNPX_DomainName; struct _tagpropertykey *
0x180005ac8  mov     rcx, r12; struct IFunctionInstance *
0x180005acb  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAPEAG@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,ushort * *)
0x180005ad0  test    eax, eax
0x180005ad2  js      short loc_180005B07
0x180005ad4  mov     rcx, [rbp+arg_18]
0x180005ad8  inc     r14
0x180005adb  cmp     [rcx+r14*2], r13w
0x180005ae0  jnz     short loc_180005AD8
0x180005ae2  cmp     r14, 2
0x180005ae6  jbe     short loc_180005AFB
0x180005ae8  add     rcx, 4; psz
0x180005aec  mov     rdx, rsi; ppwsz
0x180005aef  call    cs:__imp_SHStrDupW
0x180005af5  mov     rcx, [rbp+arg_18]; pv
0x180005af9  mov     ebx, eax
0x180005afb  call    cs:__imp_CoTaskMemFree
0x180005b01  test    ebx, ebx
0x180005b03  jns     short loc_180005B25
0x180005b05  jmp     short loc_180005B0D
0x180005b07  mov     ebx, edi
0x180005b09  jmp     short loc_180005B65
0x180005b0b  mov     ebx, edi
0x180005b0d  mov     rcx, [r15]; pv
0x180005b10  call    cs:__imp_CoTaskMemFree
0x180005b16  mov     [r15], r13
0x180005b19  mov     rcx, [rsi]; pv
0x180005b1c  call    cs:__imp_CoTaskMemFree
0x180005b22  mov     [rsi], r13
0x180005b25  cmp     ebx, 80070648h
0x180005b2b  jnz     short loc_180005B65
0x180005b2d  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x180005b31  mov     [rbp+arg_8], r13
0x180005b35  lea     rdx, PKEY_PUBSVCS_METADATA; struct _tagpropertykey *
0x180005b3c  mov     rcx, r12; struct IFunctionInstance *
0x180005b3f  call    ?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAPEAG@Z; GetFIProperty(IFunctionInstance *,_tagpropertykey const &,ushort * *)
0x180005b44  mov     ebx, eax
0x180005b46  test    eax, eax
0x180005b48  js      short loc_180005B65
0x180005b4a  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x180005b4e  mov     r8, rsi; unsigned __int16 **
0x180005b51  mov     rdx, r15; unsigned __int16 **
0x180005b54  call    ?ParsePubsubString@@YAJPEBGPEAPEAG1@Z; ParsePubsubString(ushort const *,ushort * *,ushort * *)
0x180005b59  mov     rcx, [rbp+arg_8]; pv
0x180005b5d  mov     ebx, eax
0x180005b5f  call    cs:__imp_CoTaskMemFree
0x180005b65  mov     eax, ebx
0x180005b67  mov     rbx, [rsp+20h+arg_0]
0x180005b6c  add     rsp, 20h
0x180005b70  pop     r15
0x180005b72  pop     r14
0x180005b74  pop     r13
0x180005b76  pop     r12
0x180005b78  pop     rdi
0x180005b79  pop     rsi
0x180005b7a  pop     rbp
0x180005b7b  retn
```
