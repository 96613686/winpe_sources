# CInkStrokeDisp::GetPacketValuesByProperty(ushort *,long,long,tagVARIANT *)

- ea: `0x1800cfed0`
- end: `0x1800d0129`
- name: `?GetPacketValuesByProperty@CInkStrokeDisp@@UEAAJPEAGJJPEAUtagVARIANT@@@Z`
- size: `601`
- prototype: `int(CInkStrokeDisp *__hidden this, unsigned __int16 *, int, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b78c`
- `0x18007dd94`
- `0x1800a38dc`
- `0x1800cfed0`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d00e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d00ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d00fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d00e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d00ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d00fe`
- `OLEAUT32!__imp_VariantInit` at `0x1800cff80`
- `OLEAUT32!__imp_VariantInit` at `0x1800cff80`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d007e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d007e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d0026`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d0026`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d005f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d005f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d0010`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d0010`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800cffa9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800cffa9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800cff4a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800cff4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkStrokeDisp::GetPacketValuesByProperty(
        struct CStrokeWithInk **this,
        unsigned __int16 *a2,
        int a3,
        unsigned int a4,
        struct tagVARIANT *pvarg)
{
  signed int v5; // edi
  HANDLE *v9; // rsi
  int v10; // ebx
  HRESULT v11; // eax
  unsigned int v12; // r8d
  const unsigned __int16 *v13; // r9
  int PacketPropertyData; // eax
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v16; // rdi
  HRESULT v17; // eax
  unsigned int v19; // [rsp+40h] [rbp-78h] BYREF
  DWORD dwindex[2]; // [rsp+48h] [rbp-70h] BYREF
  HANDLE *v21; // [rsp+50h] [rbp-68h]
  __int64 v22; // [rsp+58h] [rbp-60h]
  GUID pclsid; // [rsp+60h] [rbp-58h] BYREF

  v5 = a4;
  v19 = a4;
  v22 = (unsigned __int64)(this + 3) & ((unsigned __int128)-(__int128)(unsigned __int64)(this - 1) >> 64);
  dwindex[0] = 0;
  v9 = (HANDLE *)(v22 + 8);
  v21 = (HANDLE *)(v22 + 8);
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)(v22 + 8), dwindex);
  if ( a3 >= 0 && v5 >= -1 && v5 )
  {
    if ( a2 && pvarg )
    {
      VariantInit(pvarg);
      v10 = ValidateStroke(this[6]);
      if ( v10 >= 0 )
      {
        pclsid = 0;
        v11 = CLSIDFromString(a2, &pclsid);
        v10 = v11;
        if ( v11 < 0 )
        {
          if ( v11 == -2147221005 )
          {
            try
            {
              v10 = ATL::AtlSetErrorInfo(
                      &CLSID_InkStroke,
                      (const unsigned __int16 *)0x46D,
                      v12,
                      v13,
                      &IID_IInkStroke,
                      -2147221005,
                      hInstance);
            }
            catch ( ... )
            {
              v19 = ReportWispException();
              v10 = v19;
              v9 = v21;
            }
          }
        }
        else
        {
          dwindex[0] = 0;
          PacketPropertyData = InkStroke_GetPacketPropertyData(
                                 *(CInkStroke **)(*((_QWORD *)this[6] + 2) + 16LL),
                                 &pclsid,
                                 a3,
                                 dwindex,
                                 0);
          v10 = PacketPropertyData;
          if ( PacketPropertyData < 0 )
          {
            if ( PacketPropertyData == -2147220927 )
              v10 = -2147024809;
          }
          else
          {
            if ( v5 == -1 || dwindex[0] < v5 )
            {
              v5 = dwindex[0];
              v19 = dwindex[0];
            }
            *(_QWORD *)dwindex = 0;
            Vector = SafeArrayCreateVector(3u, 0, v5);
            v16 = Vector;
            if ( Vector )
            {
              v10 = SafeArrayAccessData(Vector, (void **)dwindex);
              if ( v10 < 0
                || (v10 = InkStroke_GetPacketPropertyData(
                            *(CInkStroke **)(*((_QWORD *)this[6] + 2) + 16LL),
                            &pclsid,
                            a3,
                            &v19,
                            *(int **)dwindex),
                    v17 = SafeArrayUnaccessData(v16),
                    v10 < 0)
                || (v10 = v17, v17 < 0) )
              {
                SafeArrayDestroy(v16);
              }
              else
              {
                pvarg->vt = 8195;
                pvarg->llVal = (LONGLONG)v16;
              }
            }
            else
            {
              v10 = -2147024882;
            }
          }
        }
      }
      ReleaseMutex(*v9);
      return (unsigned int)v10;
    }
    else
    {
      ReleaseMutex(*v9);
      return 2147500035LL;
    }
  }
  else
  {
    ReleaseMutex(*v9);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800cfed0  push    rbx
0x1800cfed2  push    rsi
0x1800cfed3  push    rdi
0x1800cfed4  push    r12
0x1800cfed6  push    r13
0x1800cfed8  push    r14
0x1800cfeda  push    r15
0x1800cfedc  sub     rsp, 80h
0x1800cfee3  mov     rax, cs:__security_cookie
0x1800cfeea  xor     rax, rsp
0x1800cfeed  mov     [rsp+0B8h+var_48], rax
0x1800cfef2  mov     edi, r9d
0x1800cfef5  mov     r13d, r8d
0x1800cfef8  mov     r12, rdx
0x1800cfefb  mov     r15, rcx
0x1800cfefe  mov     r14, [rsp+0B8h+pvarg]
0x1800cff06  mov     [rsp+0B8h+var_78], r9d
0x1800cff0b  lea     rax, [rcx-8]
0x1800cff0f  add     rcx, 18h
0x1800cff13  neg     rax
0x1800cff16  sbb     rdx, rdx
0x1800cff19  and     rdx, rcx
0x1800cff1c  mov     [rsp+0B8h+var_60], rdx
0x1800cff21  mov     [rsp+0B8h+dwindex], 0
0x1800cff29  lea     rsi, [rdx+8]
0x1800cff2d  mov     [rsp+0B8h+var_68], rsi
0x1800cff32  lea     rax, [rsp+0B8h+dwindex]
0x1800cff37  mov     [rsp+0B8h+lpdwindex], rax; lpdwindex
0x1800cff3c  mov     r9, rsi; pHandles
0x1800cff3f  mov     r8d, 1; cHandles
0x1800cff45  or      edx, 0FFFFFFFFh; dwTimeout
0x1800cff48  xor     ecx, ecx; dwFlags
0x1800cff4a  call    cs:__imp_CoWaitForMultipleHandles
0x1800cff50  nop
0x1800cff51  test    r13d, r13d
0x1800cff54  js      loc_1800D00FB
0x1800cff5a  cmp     edi, 0FFFFFFFFh
0x1800cff5d  jl      loc_1800D00FB
0x1800cff63  test    edi, edi
0x1800cff65  jz      loc_1800D00FB
0x1800cff6b  test    r12, r12
0x1800cff6e  jz      loc_1800D00EB
0x1800cff74  test    r14, r14
0x1800cff77  jz      loc_1800D00EB
0x1800cff7d  mov     rcx, r14; pvarg
0x1800cff80  call    cs:__imp_VariantInit
0x1800cff86  mov     rcx, [r15+30h]; struct CStrokeWithInk *
0x1800cff8a  call    ?ValidateStroke@@YAJPEAVCStrokeWithInk@@@Z; ValidateStroke(CStrokeWithInk *)
0x1800cff8f  mov     ebx, eax
0x1800cff91  test    eax, eax
0x1800cff93  js      loc_1800D00D3
0x1800cff99  xorps   xmm0, xmm0
0x1800cff9c  movups  xmmword ptr [rsp+0B8h+pclsid.Data1], xmm0
0x1800cffa1  lea     rdx, [rsp+0B8h+pclsid]; pclsid
0x1800cffa6  mov     rcx, r12; lpsz
0x1800cffa9  call    cs:__imp_CLSIDFromString
0x1800cffaf  mov     ebx, eax
0x1800cffb1  xor     r12d, r12d
0x1800cffb4  test    eax, eax
0x1800cffb6  js      loc_1800D009B
0x1800cffbc  mov     [rsp+0B8h+dwindex], r12d
0x1800cffc1  mov     rax, [r15+30h]
0x1800cffc5  mov     rcx, [rax+10h]
0x1800cffc9  mov     [rsp+0B8h+lpdwindex], r12; int *
0x1800cffce  lea     r9, [rsp+0B8h+dwindex]; unsigned int *
0x1800cffd3  mov     r8d, r13d; int
0x1800cffd6  lea     rdx, [rsp+0B8h+pclsid]; struct _GUID *
0x1800cffdb  mov     rcx, [rcx+10h]; this
0x1800cffdf  call    InkStroke_GetPacketPropertyData
0x1800cffe4  mov     ebx, eax
0x1800cffe6  test    eax, eax
0x1800cffe8  js      loc_1800D008D
0x1800cffee  mov     eax, [rsp+0B8h+dwindex]
0x1800cfff2  cmp     edi, 0FFFFFFFFh
0x1800cfff5  jz      short loc_1800CFFFB
0x1800cfff7  cmp     eax, edi
0x1800cfff9  jnb     short loc_1800D0001
0x1800cfffb  mov     edi, eax
0x1800cfffd  mov     [rsp+0B8h+var_78], eax
0x1800d0001  mov     qword ptr [rsp+0B8h+dwindex], r12
0x1800d0006  mov     ecx, 3; vt
0x1800d000b  mov     r8d, edi; cElements
0x1800d000e  xor     edx, edx; lLbound
0x1800d0010  call    cs:__imp_SafeArrayCreateVector
0x1800d0016  mov     rdi, rax
0x1800d0019  test    rax, rax
0x1800d001c  jz      short loc_1800D0086
0x1800d001e  lea     rdx, [rsp+0B8h+dwindex]; ppvData
0x1800d0023  mov     rcx, rax; psa
0x1800d0026  call    cs:__imp_SafeArrayAccessData
0x1800d002c  mov     ebx, eax
0x1800d002e  test    eax, eax
0x1800d0030  js      short loc_1800D007B
0x1800d0032  mov     rcx, [r15+30h]
0x1800d0036  mov     rcx, [rcx+10h]
0x1800d003a  mov     rdx, qword ptr [rsp+0B8h+dwindex]
0x1800d003f  mov     [rsp+0B8h+lpdwindex], rdx; int *
0x1800d0044  lea     r9, [rsp+0B8h+var_78]; unsigned int *
0x1800d0049  mov     r8d, r13d; int
0x1800d004c  lea     rdx, [rsp+0B8h+pclsid]; struct _GUID *
0x1800d0051  mov     rcx, [rcx+10h]; this
0x1800d0055  call    InkStroke_GetPacketPropertyData
0x1800d005a  mov     ebx, eax
0x1800d005c  mov     rcx, rdi; psa
0x1800d005f  call    cs:__imp_SafeArrayUnaccessData
0x1800d0065  test    ebx, ebx
0x1800d0067  js      short loc_1800D007B
0x1800d0069  mov     ebx, eax
0x1800d006b  test    eax, eax
0x1800d006d  js      short loc_1800D007B
0x1800d006f  mov     word ptr [r14], 2003h
0x1800d0075  mov     [r14+8], rdi
0x1800d0079  jmp     short loc_1800D00D3
0x1800d007b  mov     rcx, rdi; psa
0x1800d007e  call    cs:__imp_SafeArrayDestroy
0x1800d0084  jmp     short loc_1800D00D3
0x1800d0086  mov     ebx, 8007000Eh
0x1800d008b  jmp     short loc_1800D00D3
0x1800d008d  cmp     eax, 80040241h
0x1800d0092  jnz     short loc_1800D00D3
0x1800d0094  mov     ebx, 80070057h
0x1800d0099  jmp     short loc_1800D00D3
0x1800d009b  mov     ecx, 800401F3h
0x1800d00a0  cmp     eax, ecx
0x1800d00a2  jnz     short loc_1800D00D3
0x1800d00a4  mov     rax, cs:hInstance
0x1800d00ab  mov     [rsp+0B8h+var_88], rax; HINSTANCE
0x1800d00b0  mov     [rsp+0B8h+var_90], ecx; int
0x1800d00b4  lea     rax, IID_IInkStroke
0x1800d00bb  mov     [rsp+0B8h+lpdwindex], rax; struct _GUID *
0x1800d00c0  mov     edx, 46Dh; unsigned __int16 *
0x1800d00c5  lea     rcx, CLSID_InkStroke; clsid
0x1800d00cc  call    ?AtlSetErrorInfo@ATL@@YAJAEBU_GUID@@PEBGK10JPEAUHINSTANCE__@@@Z; ATL::AtlSetErrorInfo(_GUID const &,ushort const *,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *)
0x1800d00d1  mov     ebx, eax
0x1800d00d3  jmp     short loc_1800D00DE
0x1800d00d5  mov     ebx, [rsp+0B8h+var_78]
0x1800d00d9  mov     rsi, [rsp+0B8h+var_68]
0x1800d00de  mov     rcx, [rsi]; hMutex
0x1800d00e1  call    cs:__imp_ReleaseMutex
0x1800d00e7  mov     eax, ebx
0x1800d00e9  jmp     short loc_1800D0109
0x1800d00eb  mov     rcx, [rsi]; hMutex
0x1800d00ee  call    cs:__imp_ReleaseMutex
0x1800d00f4  mov     eax, 80004003h
0x1800d00f9  jmp     short loc_1800D0109
0x1800d00fb  mov     rcx, [rsi]; hMutex
0x1800d00fe  call    cs:__imp_ReleaseMutex
0x1800d0104  mov     eax, 80070057h
0x1800d0109  mov     rcx, [rsp+0B8h+var_48]
0x1800d010e  xor     rcx, rsp; StackCookie
0x1800d0111  call    __security_check_cookie
0x1800d0116  add     rsp, 80h
0x1800d011d  pop     r15
0x1800d011f  pop     r14
0x1800d0121  pop     r13
0x1800d0123  pop     r12
0x1800d0125  pop     rdi
0x1800d0126  pop     rsi
0x1800d0127  pop     rbx
0x1800d0128  retn
```
