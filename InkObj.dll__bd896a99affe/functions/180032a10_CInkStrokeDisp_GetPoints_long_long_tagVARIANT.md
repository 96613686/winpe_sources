# CInkStrokeDisp::GetPoints(long,long,tagVARIANT *)

- ea: `0x180032a10`
- end: `0x180032bcb`
- name: `?GetPoints@CInkStrokeDisp@@UEAAJJJPEAUtagVARIANT@@@Z`
- size: `443`
- prototype: `int(CInkStrokeDisp *__hidden this, int, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b78c`
- `0x180032a10`
- `0x18007de60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180032b8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180032b9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180032bab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180032b8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180032b9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180032bab`
- `OLEAUT32!__imp_VariantInit` at `0x180032a90`
- `OLEAUT32!__imp_VariantInit` at `0x180032a90`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180032b73`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180032b73`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180032b22`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180032b22`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180032b54`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180032b54`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180032b0c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180032b0c`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180032a64`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180032a64`

## pseudocode

```c
__int64 __fastcall CInkStrokeDisp::GetPoints(
        struct CStrokeWithInk **this,
        int a2,
        signed int a3,
        struct tagVARIANT *a4)
{
  __int64 v8; // rsi
  __int64 v9; // rcx
  HRESULT Points; // ebx
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v12; // rdi
  HRESULT v13; // eax
  void *ppvData; // [rsp+70h] [rbp+8h] BYREF
  DWORD dwindex; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v17; // [rsp+80h] [rbp+18h] BYREF

  dwindex = 0;
  v8 = (__int64)(this + 4);
  if ( this == (struct CStrokeWithInk **)8 )
    v8 = 8;
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)v8, &dwindex);
  if ( a2 >= 0 && a3 >= -1 && a3 )
  {
    if ( a4 )
    {
      VariantInit(a4);
      Points = ValidateStroke(this[6]);
      if ( Points >= 0 )
      {
        dwindex = 0;
        Points = InkStroke_GetPoints(*(CInkStroke **)(*(_QWORD *)(v9 + 16) + 16LL), a2, &dwindex, 0);
        if ( Points >= 0 )
        {
          if ( dwindex < a3 )
            a3 = dwindex;
          v17 = a3;
          ppvData = 0;
          if ( (unsigned int)(2 * a3) >= (unsigned __int64)(2LL * a3) )
          {
            Vector = SafeArrayCreateVector(3u, 0, 2 * a3);
            v12 = Vector;
            if ( Vector )
            {
              Points = SafeArrayAccessData(Vector, &ppvData);
              if ( Points < 0
                || (Points = InkStroke_GetPoints(
                               *(CInkStroke **)(*((_QWORD *)this[6] + 2) + 16LL),
                               a2,
                               &v17,
                               (struct tagPOINT *)ppvData),
                    v13 = SafeArrayUnaccessData(v12),
                    Points < 0)
                || (Points = v13, v13 < 0) )
              {
                SafeArrayDestroy(v12);
              }
              else
              {
                a4->vt = 8195;
                a4->llVal = (LONGLONG)v12;
              }
            }
            else
            {
              Points = -2147024882;
            }
          }
          else
          {
            Points = -2147418113;
          }
        }
      }
      ReleaseMutex(*(HANDLE *)v8);
      return (unsigned int)Points;
    }
    else
    {
      ReleaseMutex(*(HANDLE *)v8);
      return 2147500035LL;
    }
  }
  else
  {
    ReleaseMutex(*(HANDLE *)v8);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180032a10  mov     [rsp+arg_18], rbx
0x180032a15  push    rsi
0x180032a16  push    rdi
0x180032a17  push    r12
0x180032a19  push    r14
0x180032a1b  push    r15
0x180032a1d  sub     rsp, 40h
0x180032a21  mov     r14, r9
0x180032a24  mov     edi, r8d
0x180032a27  mov     r12d, edx
0x180032a2a  mov     r15, rcx
0x180032a2d  mov     [rsp+68h+dwindex], 0
0x180032a35  lea     rax, [rcx-8]
0x180032a39  lea     rsi, [rcx+20h]
0x180032a3d  mov     ecx, 8
0x180032a42  test    rax, rax
0x180032a45  cmovz   rsi, rcx
0x180032a49  mov     [rsp+68h+var_38], rsi
0x180032a4e  lea     rax, [rsp+68h+dwindex]
0x180032a53  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x180032a58  mov     r9, rsi; pHandles
0x180032a5b  lea     r8d, [rcx-7]; cHandles
0x180032a5f  or      edx, 0FFFFFFFFh; dwTimeout
0x180032a62  xor     ecx, ecx; dwFlags
0x180032a64  call    cs:__imp_CoWaitForMultipleHandles
0x180032a6a  test    r12d, r12d
0x180032a6d  js      loc_180032BA8
0x180032a73  cmp     edi, 0FFFFFFFFh
0x180032a76  jl      loc_180032BA8
0x180032a7c  test    edi, edi
0x180032a7e  jz      loc_180032BA8
0x180032a84  test    r14, r14
0x180032a87  jz      loc_180032B98
0x180032a8d  mov     rcx, r14; pvarg
0x180032a90  call    cs:__imp_VariantInit
0x180032a96  mov     rcx, [r15+30h]; struct CStrokeWithInk *
0x180032a9a  call    ?ValidateStroke@@YAJPEAVCStrokeWithInk@@@Z; ValidateStroke(CStrokeWithInk *)
0x180032a9f  mov     ebx, eax
0x180032aa1  test    eax, eax
0x180032aa3  js      loc_180032B80
0x180032aa9  mov     [rsp+68h+dwindex], 0
0x180032ab1  mov     rcx, [rcx+10h]
0x180032ab5  xor     r9d, r9d; struct tagPOINT *
0x180032ab8  lea     r8, [rsp+68h+dwindex]; unsigned int *
0x180032abd  mov     edx, r12d; int
0x180032ac0  mov     rcx, [rcx+10h]; this
0x180032ac4  call    InkStroke_GetPoints
0x180032ac9  mov     ebx, eax
0x180032acb  test    eax, eax
0x180032acd  js      loc_180032B80
0x180032ad3  cmp     [rsp+68h+dwindex], edi
0x180032ad7  cmovb   edi, [rsp+68h+dwindex]
0x180032adc  mov     [rsp+68h+arg_10], edi
0x180032ae3  mov     [rsp+68h+ppvData], 0
0x180032aec  lea     r8d, [rdi+rdi]; cElements
0x180032af0  movsxd  rcx, edi
0x180032af3  add     rcx, rcx
0x180032af6  mov     eax, r8d
0x180032af9  cmp     rax, rcx
0x180032afc  jnb     short loc_180032B05
0x180032afe  mov     ebx, 8000FFFFh
0x180032b03  jmp     short loc_180032B80
0x180032b05  mov     ecx, 3; vt
0x180032b0a  xor     edx, edx; lLbound
0x180032b0c  call    cs:__imp_SafeArrayCreateVector
0x180032b12  mov     rdi, rax
0x180032b15  test    rax, rax
0x180032b18  jz      short loc_180032B7B
0x180032b1a  lea     rdx, [rsp+68h+ppvData]; ppvData
0x180032b1f  mov     rcx, rax; psa
0x180032b22  call    cs:__imp_SafeArrayAccessData
0x180032b28  mov     ebx, eax
0x180032b2a  test    eax, eax
0x180032b2c  js      short loc_180032B70
0x180032b2e  mov     rcx, [r15+30h]
0x180032b32  mov     rcx, [rcx+10h]
0x180032b36  mov     r9, [rsp+68h+ppvData]; struct tagPOINT *
0x180032b3b  lea     r8, [rsp+68h+arg_10]; unsigned int *
0x180032b43  mov     edx, r12d; int
0x180032b46  mov     rcx, [rcx+10h]; this
0x180032b4a  call    InkStroke_GetPoints
0x180032b4f  mov     ebx, eax
0x180032b51  mov     rcx, rdi; psa
0x180032b54  call    cs:__imp_SafeArrayUnaccessData
0x180032b5a  test    ebx, ebx
0x180032b5c  js      short loc_180032B70
0x180032b5e  mov     ebx, eax
0x180032b60  test    eax, eax
0x180032b62  js      short loc_180032B70
0x180032b64  mov     word ptr [r14], 2003h
0x180032b6a  mov     [r14+8], rdi
0x180032b6e  jmp     short loc_180032B80
0x180032b70  mov     rcx, rdi; psa
0x180032b73  call    cs:__imp_SafeArrayDestroy
0x180032b79  jmp     short loc_180032B80
0x180032b7b  mov     ebx, 8007000Eh
0x180032b80  jmp     short loc_180032B8B
0x180032b82  mov     ebx, [rsp+68h+dwindex]
0x180032b86  mov     rsi, [rsp+68h+var_38]
0x180032b8b  mov     rcx, [rsi]; hMutex
0x180032b8e  call    cs:__imp_ReleaseMutex
0x180032b94  mov     eax, ebx
0x180032b96  jmp     short loc_180032BB6
0x180032b98  mov     rcx, [rsi]; hMutex
0x180032b9b  call    cs:__imp_ReleaseMutex
0x180032ba1  mov     eax, 80004003h
0x180032ba6  jmp     short loc_180032BB6
0x180032ba8  mov     rcx, [rsi]; hMutex
0x180032bab  call    cs:__imp_ReleaseMutex
0x180032bb1  mov     eax, 80070057h
0x180032bb6  mov     rbx, [rsp+68h+arg_18]
0x180032bbe  add     rsp, 40h
0x180032bc2  pop     r15
0x180032bc4  pop     r14
0x180032bc6  pop     r12
0x180032bc8  pop     rdi
0x180032bc9  pop     rsi
0x180032bca  retn
```
