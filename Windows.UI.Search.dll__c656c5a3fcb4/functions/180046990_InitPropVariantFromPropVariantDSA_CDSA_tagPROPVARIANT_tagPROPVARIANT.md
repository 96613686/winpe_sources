# InitPropVariantFromPropVariantDSA(CDSA<tagPROPVARIANT> *,tagPROPVARIANT *)

- ea: `0x180046990`
- end: `0x180046bda`
- name: `?InitPropVariantFromPropVariantDSA@@YAJPEAV?$CDSA@UtagPROPVARIANT@@@@PEAUtagPROPVARIANT@@@Z`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800462e0`

## callees

- `0x180044020`
- `0x180046990`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046b09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046b09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046a3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046a3a`
- `PROPSYS!PropVariantToStringAlloc` at `0x180046b6a`
- `PROPSYS!PropVariantToStringAlloc` at `0x180046b6a`
- `COMCTL32!__imp_DSA_GetItemPtr` at `0x1800469ed`
- `COMCTL32!__imp_DSA_GetItemPtr` at `0x180046a72`
- `COMCTL32!__imp_DSA_GetItemPtr` at `0x1800469ed`
- `COMCTL32!__imp_DSA_GetItemPtr` at `0x180046a72`

## pseudocode

```c
__int64 __fastcall InitPropVariantFromPropVariantDSA(HDSA *a1, __int64 a2)
{
  int v2; // r14d
  HRESULT v5; // edi
  struct _DSA *v6; // rcx
  int v7; // ebx
  unsigned __int16 v8; // r15
  int v9; // eax
  int v10; // r9d
  int v11; // eax
  void *v12; // rsi
  int v13; // ebx
  const PROPVARIANT *ItemPtr; // rax
  _OWORD *v15; // rcx
  __int128 v17; // [rsp+20h] [rbp-20h]
  int v18; // [rsp+80h] [rbp+40h]
  PWSTR ppszOut; // [rsp+90h] [rbp+50h] BYREF

  v2 = 0;
  v5 = -2147024809;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  if ( a1 )
  {
    v6 = *a1;
    v5 = 0;
    if ( v6 )
    {
      v7 = *(_DWORD *)v6;
      v18 = *(_DWORD *)v6;
      if ( *(_DWORD *)v6 )
      {
        v5 = -2147286953;
        v8 = *(_WORD *)DSA_GetItemPtr(v6, 0);
        if ( v8 == 8 )
        {
          v8 = 31;
        }
        else if ( (v8 & 0x1000) != 0 )
        {
          return (unsigned int)v5;
        }
        v9 = CRGTypeSizes::operator[](8, v8);
        v11 = v10 & v9;
        if ( v11 )
        {
          v5 = -2147024882;
          v17 = 0;
          v12 = CoTaskMemAlloc((unsigned int)(v7 * v11));
          if ( v12 )
          {
            v13 = 0;
            DWORD2(v17) = 0;
            v5 = 0;
            while ( 1 )
            {
              if ( v2 >= v18 )
              {
                LOWORD(v17) = v8 | 0x1000;
                *(_OWORD *)a2 = v17;
                *(_QWORD *)(a2 + 16) = v12;
                return (unsigned int)v5;
              }
              ItemPtr = (const PROPVARIANT *)DSA_GetItemPtr(*a1, v2);
              if ( *(_WORD *)ItemPtr != v8 )
              {
                if ( *(_WORD *)ItemPtr == 8 )
                {
                  if ( v8 != 31 )
                    goto LABEL_26;
                }
                else if ( (*(_WORD *)ItemPtr || v8 != 1) && (*(_WORD *)ItemPtr != 1 || v8) )
                {
LABEL_26:
                  v5 = -2147286953;
LABEL_27:
                  CoTaskMemFree(v12);
                  return (unsigned int)v5;
                }
              }
              if ( v8 > 0x13u )
              {
                switch ( v8 )
                {
                  case 0x14u:
                  case 0x15u:
                    goto LABEL_39;
                  case 0x1Fu:
                    ppszOut = 0;
                    v5 = PropVariantToStringAlloc(ItemPtr, &ppszOut);
                    if ( v5 >= 0 )
                    {
                      *((_QWORD *)v12 + v2) = ppszOut;
                      DWORD2(v17) = ++v13;
                    }
                    goto LABEL_41;
                  case 0x40u:
LABEL_39:
                    *((PROPVARIANT *)v12 + v2) = ItemPtr[1];
                    goto LABEL_40;
                  case 0x48u:
                    v15 = (_OWORD *)*((_QWORD *)ItemPtr + 1);
                    if ( v15 )
                    {
                      v5 = 0;
                      *((_OWORD *)v12 + v2) = *v15;
                      goto LABEL_40;
                    }
                    break;
                }
              }
              else
              {
                switch ( v8 )
                {
                  case 0x13u:
                    goto LABEL_28;
                  case 2u:
                    goto LABEL_21;
                  case 3u:
LABEL_28:
                    *((_DWORD *)v12 + v2) = *((_DWORD *)ItemPtr + 2);
                    goto LABEL_40;
                  case 5u:
                    goto LABEL_39;
                  case 0xBu:
                  case 0x12u:
LABEL_21:
                    *((_WORD *)v12 + v2) = *((_WORD *)ItemPtr + 4);
LABEL_40:
                    DWORD2(v17) = ++v13;
                    goto LABEL_41;
                }
              }
              v5 = -2147286953;
LABEL_41:
              ++v2;
              if ( v5 < 0 )
                goto LABEL_27;
            }
          }
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180046990  mov     [rsp-38h+arg_8], rbx
0x180046995  push    rbp
0x180046996  push    rsi
0x180046997  push    rdi
0x180046998  push    r12
0x18004699a  push    r13
0x18004699c  push    r14
0x18004699e  push    r15
0x1800469a0  mov     rbp, rsp
0x1800469a3  sub     rsp, 40h
0x1800469a7  xor     eax, eax
0x1800469a9  xorps   xmm0, xmm0
0x1800469ac  xor     r14d, r14d
0x1800469af  mov     r13, rdx
0x1800469b2  mov     r12, rcx
0x1800469b5  mov     edi, 80070057h
0x1800469ba  movups  xmmword ptr [rdx], xmm0
0x1800469bd  mov     [rdx+10h], rax
0x1800469c1  test    rcx, rcx
0x1800469c4  jz      loc_180046BC0
0x1800469ca  mov     rcx, [rcx]; hdsa
0x1800469cd  mov     edi, r14d
0x1800469d0  test    rcx, rcx
0x1800469d3  jz      loc_180046BC0
0x1800469d9  mov     ebx, [rcx]
0x1800469db  mov     [rbp+arg_0], ebx
0x1800469de  test    ebx, ebx
0x1800469e0  jz      loc_180046BC0
0x1800469e6  xor     edx, edx; i
0x1800469e8  mov     edi, 80030057h
0x1800469ed  call    cs:__imp_DSA_GetItemPtr
0x1800469f3  lea     ecx, [r14+8]
0x1800469f7  lea     r9d, [r14+1Fh]
0x1800469fb  movzx   r15d, word ptr [rax]
0x1800469ff  cmp     r15w, cx
0x180046a03  jnz     short loc_180046A0B
0x180046a05  movzx   r15d, r9w
0x180046a09  jmp     short loc_180046A17
0x180046a0b  bt      r15w, 0Ch
0x180046a11  jb      loc_180046BC0
0x180046a17  movzx   edx, r15w
0x180046a1b  call    ??ACRGTypeSizes@@QEAAGH@Z; CRGTypeSizes::operator[](int)
0x180046a20  and     eax, r9d
0x180046a23  jz      loc_180046BC0
0x180046a29  imul    eax, ebx
0x180046a2c  xorps   xmm0, xmm0
0x180046a2f  mov     edi, 8007000Eh
0x180046a34  movups  [rbp+var_20], xmm0
0x180046a38  mov     ecx, eax; cb
0x180046a3a  call    cs:__imp_CoTaskMemAlloc
0x180046a40  mov     rsi, rax
0x180046a43  test    rax, rax
0x180046a46  jz      loc_180046BC0
0x180046a4c  movzx   eax, r15w
0x180046a50  mov     ebx, r14d
0x180046a53  or      ax, 1000h
0x180046a57  mov     dword ptr [rbp+var_20+8], ebx
0x180046a5a  mov     word ptr [rbp+var_20], ax
0x180046a5e  mov     edi, r14d
0x180046a61  cmp     r14d, [rbp+arg_0]
0x180046a65  jge     loc_180046BB3
0x180046a6b  mov     rcx, [r12]; hdsa
0x180046a6f  mov     edx, r14d; i
0x180046a72  call    cs:__imp_DSA_GetItemPtr
0x180046a78  mov     r8, rax
0x180046a7b  mov     edx, 8
0x180046a80  cmp     [rax], r15w
0x180046a84  jz      short loc_180046A94
0x180046a86  cmp     [rax], dx
0x180046a89  lea     eax, [rdx+17h]
0x180046a8c  jnz     short loc_180046AD6
0x180046a8e  cmp     r15w, ax
0x180046a92  jnz     short loc_180046B01
0x180046a94  xor     r9d, r9d
0x180046a97  lea     r10d, [r9+1]
0x180046a9b  cmp     r15w, 13h
0x180046aa0  ja      short loc_180046B20
0x180046aa2  jz      short loc_180046B14
0x180046aa4  movzx   ecx, r15w
0x180046aa8  sub     ecx, 2
0x180046aab  jz      short loc_180046AC5
0x180046aad  sub     ecx, 1
0x180046ab0  jz      short loc_180046B14
0x180046ab2  sub     ecx, 2
0x180046ab5  jz      loc_180046B8D
0x180046abb  sub     ecx, 6
0x180046abe  jz      short loc_180046AC5
0x180046ac0  cmp     ecx, 7
0x180046ac3  jnz     short loc_180046B3C
0x180046ac5  movzx   eax, word ptr [r8+8]
0x180046aca  movsxd  rcx, r14d
0x180046acd  mov     [rsi+rcx*2], ax
0x180046ad1  jmp     loc_180046B98
0x180046ad6  cmp     [r8], ax
0x180046ada  jnz     short loc_180046AE2
0x180046adc  cmp     r15w, dx
0x180046ae0  jz      short loc_180046A94
0x180046ae2  xor     r9d, r9d
0x180046ae5  lea     r10d, [r9+1]
0x180046ae9  cmp     [r8], r9w
0x180046aed  jnz     short loc_180046AF5
0x180046aef  cmp     r15w, r10w
0x180046af3  jz      short loc_180046A9B
0x180046af5  cmp     [r8], r10w
0x180046af9  jnz     short loc_180046B01
0x180046afb  test    r15w, r15w
0x180046aff  jz      short loc_180046A9B
0x180046b01  mov     edi, 80030057h
0x180046b06  mov     rcx, rsi; pv
0x180046b09  call    cs:__imp_CoTaskMemFree
0x180046b0f  jmp     loc_180046BC0
0x180046b14  mov     eax, [r8+8]
0x180046b18  movsxd  rcx, r14d
0x180046b1b  mov     [rsi+rcx*4], eax
0x180046b1e  jmp     short loc_180046B98
0x180046b20  movzx   ecx, r15w
0x180046b24  sub     ecx, 14h
0x180046b27  jz      short loc_180046B8D
0x180046b29  sub     ecx, 1
0x180046b2c  jz      short loc_180046B8D
0x180046b2e  sub     ecx, 0Ah
0x180046b31  jz      short loc_180046B5F
0x180046b33  sub     ecx, 21h ; '!'
0x180046b36  jz      short loc_180046B8D
0x180046b38  cmp     ecx, edx
0x180046b3a  jz      short loc_180046B43
0x180046b3c  mov     edi, 80030057h
0x180046b41  jmp     short loc_180046B9E
0x180046b43  mov     rcx, [r8+8]
0x180046b47  test    rcx, rcx
0x180046b4a  jz      short loc_180046B3C
0x180046b4c  movups  xmm0, xmmword ptr [rcx]
0x180046b4f  movsxd  rax, r14d
0x180046b52  mov     edi, r9d
0x180046b55  add     rax, rax
0x180046b58  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x180046b5d  jmp     short loc_180046B98
0x180046b5f  lea     rdx, [rbp+ppszOut]; ppszOut
0x180046b63  mov     [rbp+ppszOut], r9
0x180046b67  mov     rcx, r8; propvar
0x180046b6a  call    cs:__imp_PropVariantToStringAlloc
0x180046b70  mov     edi, eax
0x180046b72  test    eax, eax
0x180046b74  js      short loc_180046B9E
0x180046b76  mov     rax, [rbp+ppszOut]
0x180046b7a  movsxd  rcx, r14d
0x180046b7d  mov     [rsi+rcx*8], rax
0x180046b81  mov     eax, 1
0x180046b86  add     ebx, eax
0x180046b88  mov     dword ptr [rbp+var_20+8], ebx
0x180046b8b  jmp     short loc_180046BA3
0x180046b8d  mov     rax, [r8+8]
0x180046b91  movsxd  rcx, r14d
0x180046b94  mov     [rsi+rcx*8], rax
0x180046b98  add     ebx, r10d
0x180046b9b  mov     dword ptr [rbp+var_20+8], ebx
0x180046b9e  mov     eax, 1
0x180046ba3  add     r14d, eax
0x180046ba6  test    edi, edi
0x180046ba8  jns     loc_180046A61
0x180046bae  jmp     loc_180046B06
0x180046bb3  movups  xmm0, [rbp+var_20]
0x180046bb7  movups  xmmword ptr [r13+0], xmm0
0x180046bbc  mov     [r13+10h], rsi
0x180046bc0  mov     rbx, [rsp+40h+arg_8]
0x180046bc8  mov     eax, edi
0x180046bca  add     rsp, 40h
0x180046bce  pop     r15
0x180046bd0  pop     r14
0x180046bd2  pop     r13
0x180046bd4  pop     r12
0x180046bd6  pop     rdi
0x180046bd7  pop     rsi
0x180046bd8  pop     rbp
0x180046bd9  retn
```
