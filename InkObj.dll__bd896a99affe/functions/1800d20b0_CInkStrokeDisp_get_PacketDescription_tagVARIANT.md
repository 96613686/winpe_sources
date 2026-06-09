# CInkStrokeDisp::get_PacketDescription(tagVARIANT *)

- ea: `0x1800d20b0`
- end: `0x1800d22f1`
- name: `?get_PacketDescription@CInkStrokeDisp@@UEAAJPEAUtagVARIANT@@@Z`
- size: `577`
- prototype: `int(CInkStrokeDisp *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002740`
- `0x18000b78c`
- `0x180010350`
- `0x180034e54`
- `0x1800d20b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d22c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d22d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d22c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d22d6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d222c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d222c`
- `OLEAUT32!__imp_VariantInit` at `0x1800d2117`
- `OLEAUT32!__imp_VariantInit` at `0x1800d22c0`
- `OLEAUT32!__imp_VariantInit` at `0x1800d2117`
- `OLEAUT32!__imp_VariantInit` at `0x1800d22c0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d226e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d226e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d21da`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d21da`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d2279`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d2279`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d21bd`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d21bd`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800d2217`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800d2217`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d225a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d225a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d2105`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d2105`

## pseudocode

```c
__int64 __fastcall CInkStrokeDisp::get_PacketDescription(struct CStrokeWithInk **this, struct tagVARIANT *a2)
{
  __int64 v4; // r14
  __int64 v5; // rcx
  HRESULT PacketDescription; // ebx
  signed int v7; // r13d
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v9; // rsi
  signed int v10; // r12d
  HRESULT v11; // r15d
  BSTR v12; // rax
  void *v14[2]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v15; // [rsp+40h] [rbp-48h]
  void *ppvData; // [rsp+90h] [rbp+8h] BYREF
  struct tagVARIANT *v17; // [rsp+98h] [rbp+10h]
  LPOLESTR lpsz; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+20h]

  v17 = a2;
  LODWORD(ppvData) = 0;
  v4 = (__int64)(this + 4);
  if ( this == (struct CStrokeWithInk **)8 )
    v4 = 8;
  v19 = v4;
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)v4, (LPDWORD)&ppvData);
  if ( a2 )
  {
    VariantInit(a2);
    PacketDescription = ValidateStroke(this[6]);
    if ( PacketDescription >= 0 )
    {
      *(_OWORD *)v14 = 0;
      v15 = 0;
      PacketDescription = InkStroke_GetPacketDescription(*(_QWORD *)(*(_QWORD *)(v5 + 16) + 16LL), v14);
      if ( PacketDescription >= 0 )
      {
        v7 = HIDWORD(v14[0]);
        v14[1] = WinMalloc(saturated_mul(SHIDWORD(v14[0]), 0x20u));
        if ( v14[1] )
        {
          PacketDescription = InkStroke_GetPacketDescription(*(_QWORD *)(*((_QWORD *)this[6] + 2) + 16LL), v14);
          if ( PacketDescription >= 0 )
          {
            ppvData = 0;
            Vector = SafeArrayCreateVector(8u, 0, v7);
            v9 = Vector;
            if ( Vector )
            {
              PacketDescription = SafeArrayAccessData(Vector, &ppvData);
              if ( PacketDescription < 0 )
                goto LABEL_19;
              lpsz = 0;
              v10 = 0;
              while ( v10 < v7 )
              {
                v11 = StringFromCLSID((const IID *const)v14[1] + 2 * v10, &lpsz);
                if ( v11 >= 0 )
                {
                  v12 = SysAllocString(lpsz);
                  *((_QWORD *)ppvData + v10) = v12;
                  if ( !*((_QWORD *)ppvData + v10) )
                    v11 = -2147024882;
                  CoTaskMemFree(lpsz);
                }
                ++v10;
                if ( v11 < 0 )
                {
                  PacketDescription = v11;
                  goto LABEL_19;
                }
              }
              PacketDescription = SafeArrayUnaccessData(v9);
              if ( PacketDescription < 0 )
              {
LABEL_19:
                SafeArrayDestroy(v9);
              }
              else
              {
                a2->vt = 8200;
                a2->llVal = (LONGLONG)v9;
              }
            }
            else
            {
              PacketDescription = -2147024882;
            }
          }
          WinFree(v14[1]);
        }
        else
        {
          PacketDescription = -2147024882;
        }
      }
    }
    if ( PacketDescription < 0 )
      VariantInit(a2);
    ReleaseMutex(*(HANDLE *)v4);
    return (unsigned int)PacketDescription;
  }
  else
  {
    ReleaseMutex(*(HANDLE *)v4);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800d20b0  mov     r11, rsp
0x1800d20b3  mov     [r11+10h], rdx
0x1800d20b7  push    rbx
0x1800d20b8  push    rsi
0x1800d20b9  push    rdi
0x1800d20ba  push    r12
0x1800d20bc  push    r13
0x1800d20be  push    r14
0x1800d20c0  push    r15
0x1800d20c2  sub     rsp, 50h
0x1800d20c6  mov     rdi, rdx
0x1800d20c9  mov     rsi, rcx
0x1800d20cc  mov     dword ptr [r11+8], 0
0x1800d20d4  lea     rax, [rcx-8]
0x1800d20d8  lea     r14, [rcx+20h]
0x1800d20dc  mov     r15d, 8
0x1800d20e2  test    rax, rax
0x1800d20e5  cmovz   r14, r15
0x1800d20e9  mov     [rsp+88h+arg_18], r14
0x1800d20f1  lea     rax, [r11+8]
0x1800d20f5  mov     [r11-68h], rax
0x1800d20f9  mov     r9, r14; pHandles
0x1800d20fc  lea     r8d, [r15-7]; cHandles
0x1800d2100  or      edx, 0FFFFFFFFh; dwTimeout
0x1800d2103  xor     ecx, ecx; dwFlags
0x1800d2105  call    cs:__imp_CoWaitForMultipleHandles
0x1800d210b  test    rdi, rdi
0x1800d210e  jz      loc_1800D22D3
0x1800d2114  mov     rcx, rdi; pvarg
0x1800d2117  call    cs:__imp_VariantInit
0x1800d211d  mov     rcx, [rsi+30h]; struct CStrokeWithInk *
0x1800d2121  call    ?ValidateStroke@@YAJPEAVCStrokeWithInk@@@Z; ValidateStroke(CStrokeWithInk *)
0x1800d2126  mov     ebx, eax
0x1800d2128  test    eax, eax
0x1800d212a  js      loc_1800D22A0
0x1800d2130  xorps   xmm0, xmm0
0x1800d2133  movups  xmmword ptr [rsp+88h+var_58], xmm0
0x1800d2138  movups  [rsp+88h+var_48], xmm0
0x1800d213d  mov     rcx, [rcx+10h]
0x1800d2141  lea     rdx, [rsp+88h+var_58]
0x1800d2146  mov     rcx, [rcx+10h]
0x1800d214a  call    InkStroke_GetPacketDescription
0x1800d214f  mov     ebx, eax
0x1800d2151  test    eax, eax
0x1800d2153  js      loc_1800D22A0
0x1800d2159  movsxd  r13, dword ptr [rsp+88h+var_58+4]
0x1800d215e  lea     eax, [r15+18h]
0x1800d2162  mul     r13
0x1800d2165  lea     rcx, [r15-9]
0x1800d2169  cmovb   rax, rcx
0x1800d216d  mov     rcx, rax; unsigned __int64
0x1800d2170  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800d2175  mov     [rsp+88h+var_58+8], rax
0x1800d217a  test    rax, rax
0x1800d217d  jnz     short loc_1800D2189
0x1800d217f  mov     ebx, 8007000Eh
0x1800d2184  jmp     loc_1800D22A0
0x1800d2189  mov     rax, [rsi+30h]
0x1800d218d  mov     rcx, [rax+10h]
0x1800d2191  lea     rdx, [rsp+88h+var_58]
0x1800d2196  mov     rcx, [rcx+10h]
0x1800d219a  call    InkStroke_GetPacketDescription
0x1800d219f  mov     ebx, eax
0x1800d21a1  test    eax, eax
0x1800d21a3  js      loc_1800D2295
0x1800d21a9  mov     [rsp+88h+ppvData], 0
0x1800d21b5  mov     ecx, r15d; vt
0x1800d21b8  mov     r8d, r13d; cElements
0x1800d21bb  xor     edx, edx; lLbound
0x1800d21bd  call    cs:__imp_SafeArrayCreateVector
0x1800d21c3  mov     rsi, rax
0x1800d21c6  test    rax, rax
0x1800d21c9  jz      loc_1800D2290
0x1800d21cf  lea     rdx, [rsp+88h+ppvData]; ppvData
0x1800d21d7  mov     rcx, rax; psa
0x1800d21da  call    cs:__imp_SafeArrayAccessData
0x1800d21e0  mov     ebx, eax
0x1800d21e2  test    eax, eax
0x1800d21e4  js      loc_1800D226B
0x1800d21ea  mov     [rsp+88h+lpsz], 0
0x1800d21f6  xor     r12d, r12d
0x1800d21f9  mov     ebx, 8007000Eh
0x1800d21fe  cmp     r12d, r13d
0x1800d2201  jge     short loc_1800D2276
0x1800d2203  movsxd  rcx, r12d
0x1800d2206  shl     rcx, 5
0x1800d220a  add     rcx, [rsp+88h+var_58+8]; rclsid
0x1800d220f  lea     rdx, [rsp+88h+lpsz]; lplpsz
0x1800d2217  call    cs:__imp_StringFromCLSID
0x1800d221d  mov     r15d, eax
0x1800d2220  test    eax, eax
0x1800d2222  js      short loc_1800D2260
0x1800d2224  mov     rcx, [rsp+88h+lpsz]; psz
0x1800d222c  call    cs:__imp_SysAllocString
0x1800d2232  mov     rcx, [rsp+88h+ppvData]
0x1800d223a  movsxd  rdx, r12d
0x1800d223d  mov     [rcx+rdx*8], rax
0x1800d2241  mov     rcx, [rsp+88h+ppvData]
0x1800d2249  cmp     qword ptr [rcx+rdx*8], 0
0x1800d224e  cmovz   r15d, ebx
0x1800d2252  mov     rcx, [rsp+88h+lpsz]; pv
0x1800d225a  call    cs:__imp_CoTaskMemFree
0x1800d2260  inc     r12d
0x1800d2263  test    r15d, r15d
0x1800d2266  jns     short loc_1800D21FE
0x1800d2268  mov     ebx, r15d
0x1800d226b  mov     rcx, rsi; psa
0x1800d226e  call    cs:__imp_SafeArrayDestroy
0x1800d2274  jmp     short loc_1800D2295
0x1800d2276  mov     rcx, rsi; psa
0x1800d2279  call    cs:__imp_SafeArrayUnaccessData
0x1800d227f  mov     ebx, eax
0x1800d2281  test    eax, eax
0x1800d2283  js      short loc_1800D226B
0x1800d2285  mov     word ptr [rdi], 2008h
0x1800d228a  mov     [rdi+8], rsi
0x1800d228e  jmp     short loc_1800D2295
0x1800d2290  mov     ebx, 8007000Eh
0x1800d2295  mov     rcx, [rsp+88h+var_58+8]; void *
0x1800d229a  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800d229f  nop
0x1800d22a0  jmp     short loc_1800D22B9
0x1800d22a2  mov     rdi, [rsp+88h+arg_8]
0x1800d22aa  mov     ebx, dword ptr [rsp+88h+ppvData]
0x1800d22b1  mov     r14, [rsp+88h+arg_18]
0x1800d22b9  test    ebx, ebx
0x1800d22bb  jns     short loc_1800D22C6
0x1800d22bd  mov     rcx, rdi; pvarg
0x1800d22c0  call    cs:__imp_VariantInit
0x1800d22c6  mov     rcx, [r14]; hMutex
0x1800d22c9  call    cs:__imp_ReleaseMutex
0x1800d22cf  mov     eax, ebx
0x1800d22d1  jmp     short loc_1800D22E1
0x1800d22d3  mov     rcx, [r14]; hMutex
0x1800d22d6  call    cs:__imp_ReleaseMutex
0x1800d22dc  mov     eax, 80004003h
0x1800d22e1  add     rsp, 50h
0x1800d22e5  pop     r15
0x1800d22e7  pop     r14
0x1800d22e9  pop     r13
0x1800d22eb  pop     r12
0x1800d22ed  pop     rdi
0x1800d22ee  pop     rsi
0x1800d22ef  pop     rbx
0x1800d22f0  retn
```
