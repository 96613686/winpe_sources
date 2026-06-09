# AuthHostWebInstance::OnBeforeNavigate(IHTMLWindow2 *,IUri *,IUri *,int,WebPlatformNavigationDataFlags,ushort const *,uchar const *,ulong,ushort const *,int,int *)

- ea: `0x140009e50`
- end: `0x14000a0a1`
- name: `?OnBeforeNavigate@AuthHostWebInstance@@UEAAJPEAUIHTMLWindow2@@PEAUIUri@@1HW4WebPlatformNavigationDataFlags@@PEBGPEBEK3HPEAH@Z`
- size: `593`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x140002c98`
- `0x14000429c`
- `0x1400097b0`
- `0x140009e50`
- `0x14000bd28`
- `0x14000c0c0`
- `0x14000c2dc`
- `0x14000c3dc`
- `0x14000c9c8`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000a073`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000a073`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a082`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a082`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AuthHostWebInstance::OnBeforeNavigate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        __int64 a7,
        LPCCH lpMultiByteStr,
        int cchWideChar,
        __int64 a10,
        __int64 a11,
        int *a12)
{
  int v14; // eax
  unsigned int IsTerminateNavigateUrl; // ebp
  const unsigned __int16 *v16; // rsi
  int v17; // r8d
  int v18; // edi
  __int64 v19; // rax
  PVOID v20; // rcx
  unsigned __int16 *v21; // rdi
  __int64 *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rcx
  unsigned __int16 *i; // rax
  BSTR bstrString; // [rsp+80h] [rbp+18h] BYREF

  bstrString = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a3 + 56LL))(a3, &bstrString);
  IsTerminateNavigateUrl = v14;
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        22,
        &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids,
        (unsigned int)v14);
    }
    goto LABEL_35;
  }
  v16 = bstrString;
  if ( !(unsigned __int8)IsValidWindow(a2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids, v16);
    }
    goto LABEL_35;
  }
  v18 = cchWideChar;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_SDdS(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, v17, (_DWORD)v16, a6, cchWideChar, a10);
  }
  if ( *(_DWORD *)(a1 + 124) == 2 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 96) + 96LL))(*(_QWORD *)(a1 + 96), 0);
  v19 = ConvertPostDataBytesToString(lpMultiByteStr, v18);
  v21 = (unsigned __int16 *)v19;
  if ( v19 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids, v19);
    }
    if ( (unsigned int)(*(_DWORD *)(a1 + 124) - 1) > 1 || (Microsoft_Windows_WebAuthEnableBits & 1) == 0 )
      goto LABEL_29;
    v22 = BeforePostNavigateEvent;
    goto LABEL_28;
  }
  if ( (unsigned int)(*(_DWORD *)(a1 + 124) - 1) <= 1 && (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
  {
    v22 = BeforeNavigateEvent;
LABEL_28:
    McTemplateU0z_EventWriteTransfer(v20, v22, v16);
  }
LABEL_29:
  TraceWindow(a2);
  IsTerminateNavigateUrl = AuthHostWebInstance::IsTerminateNavigateUrl((AuthHostWebInstance *)(a1 - 8), v16, v21, a12);
  if ( v21 )
  {
    v23 = -1;
    do
      ++v23;
    while ( v21[v23] );
    v24 = 2 * v23;
    for ( i = v21; v24; --v24 )
    {
      *(_BYTE *)i = 0;
      i = (unsigned __int16 *)((char *)i + 1);
    }
    LocalFree(v21);
  }
LABEL_35:
  SysFreeString(bstrString);
  return IsTerminateNavigateUrl;
}

```

## disassembly

```asm
0x140009e50  mov     r11, rsp
0x140009e53  mov     [r11+8], rbx
0x140009e57  mov     [r11+10h], rbp
0x140009e5b  push    rsi
0x140009e5c  push    rdi
0x140009e5d  push    r12
0x140009e5f  push    r14
0x140009e61  push    r15
0x140009e63  sub     rsp, 40h
0x140009e67  mov     r15, rdx
0x140009e6a  mov     r14, rcx
0x140009e6d  xor     r12d, r12d
0x140009e70  mov     [r11+18h], r12
0x140009e74  mov     rax, [r8]
0x140009e77  lea     rdx, [r11+18h]
0x140009e7b  mov     rcx, r8
0x140009e7e  mov     rax, [rax+38h]
0x140009e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e87  mov     ebp, eax
0x140009e89  test    eax, eax
0x140009e8b  jns     short loc_140009ED5
0x140009e8d  lea     rbx, WPP_GLOBAL_Control
0x140009e94  mov     rcx, cs:WPP_GLOBAL_Control
0x140009e9b  cmp     rcx, rbx
0x140009e9e  jz      loc_14000A07A
0x140009ea4  test    byte ptr [rcx+44h], 4
0x140009ea8  jz      loc_14000A07A
0x140009eae  cmp     byte ptr [rcx+41h], 5
0x140009eb2  jb      loc_14000A07A
0x140009eb8  lea     edx, [r12+16h]
0x140009ebd  mov     r9d, eax
0x140009ec0  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x140009ec7  mov     rcx, [rcx+38h]
0x140009ecb  call    WPP_SF_d
0x140009ed0  jmp     loc_14000A07A
0x140009ed5  mov     rsi, [rsp+68h+bstrString]
0x140009edd  mov     rcx, r15
0x140009ee0  call    _IsValidWindow
0x140009ee5  test    al, al
0x140009ee7  jnz     short loc_140009F31
0x140009ee9  lea     rbx, WPP_GLOBAL_Control
0x140009ef0  mov     rcx, cs:WPP_GLOBAL_Control
0x140009ef7  cmp     rcx, rbx
0x140009efa  jz      loc_14000A07A
0x140009f00  test    byte ptr [rcx+44h], 4
0x140009f04  jz      loc_14000A07A
0x140009f0a  cmp     byte ptr [rcx+41h], 5
0x140009f0e  jb      loc_14000A07A
0x140009f14  mov     edx, 17h
0x140009f19  mov     r9, rsi
0x140009f1c  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x140009f23  mov     rcx, [rcx+38h]
0x140009f27  call    WPP_SF_S
0x140009f2c  jmp     loc_14000A07A
0x140009f31  lea     rbx, WPP_GLOBAL_Control
0x140009f38  mov     edi, [rsp+68h+cchWideChar]
0x140009f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009f46  cmp     rcx, rbx
0x140009f49  jz      short loc_140009F84
0x140009f4b  test    byte ptr [rcx+44h], 4
0x140009f4f  jz      short loc_140009F84
0x140009f51  cmp     byte ptr [rcx+41h], 5
0x140009f55  jb      short loc_140009F84
0x140009f57  mov     edx, 18h
0x140009f5c  mov     rax, [rsp+68h+arg_48]
0x140009f64  mov     [rsp+68h+var_38], rax
0x140009f69  mov     [rsp+68h+var_40], edi
0x140009f6d  mov     eax, dword ptr [rsp+68h+arg_28]
0x140009f74  mov     [rsp+68h+var_48], eax
0x140009f78  mov     r9, rsi
0x140009f7b  mov     rcx, [rcx+38h]
0x140009f7f  call    WPP_SF_SDdS
0x140009f84  cmp     dword ptr [r14+7Ch], 2
0x140009f89  jnz     short loc_140009F9D
0x140009f8b  mov     rcx, [r14+60h]
0x140009f8f  mov     rax, [rcx]
0x140009f92  xor     edx, edx
0x140009f94  mov     rax, [rax+60h]
0x140009f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f9d  mov     edx, edi; cchWideChar
0x140009f9f  mov     rcx, [rsp+68h+lpMultiByteStr]; lpMultiByteStr
0x140009fa7  call    _ConvertPostDataBytesToString
0x140009fac  mov     rdi, rax
0x140009faf  test    rax, rax
0x140009fb2  jz      short loc_14000A001
0x140009fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x140009fbb  cmp     rcx, rbx
0x140009fbe  jz      short loc_140009FE4
0x140009fc0  test    byte ptr [rcx+44h], 4
0x140009fc4  jz      short loc_140009FE4
0x140009fc6  cmp     byte ptr [rcx+41h], 5
0x140009fca  jb      short loc_140009FE4
0x140009fcc  mov     edx, 19h
0x140009fd1  mov     r9, rax
0x140009fd4  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x140009fdb  mov     rcx, [rcx+38h]
0x140009fdf  call    WPP_SF_S
0x140009fe4  mov     eax, [r14+7Ch]
0x140009fe8  dec     eax
0x140009fea  cmp     eax, 1
0x140009fed  ja      short loc_14000A024
0x140009fef  test    cs:Microsoft_Windows_WebAuthEnableBits, 1
0x140009ff6  jz      short loc_14000A024
0x140009ff8  lea     rdx, BeforePostNavigateEvent
0x140009fff  jmp     short loc_14000A01C
0x14000a001  mov     eax, [r14+7Ch]
0x14000a005  dec     eax
0x14000a007  cmp     eax, 1
0x14000a00a  ja      short loc_14000A024
0x14000a00c  test    cs:Microsoft_Windows_WebAuthEnableBits, 1
0x14000a013  jz      short loc_14000A024
0x14000a015  lea     rdx, BeforeNavigateEvent
0x14000a01c  mov     r8, rsi
0x14000a01f  call    McTemplateU0z_EventWriteTransfer
0x14000a024  mov     rcx, r15
0x14000a027  call    _TraceWindow
0x14000a02c  mov     r9, [rsp+68h+arg_58]; int *
0x14000a034  mov     r8, rdi; unsigned __int16 *
0x14000a037  mov     rdx, rsi; unsigned __int16 *
0x14000a03a  lea     rcx, [r14-8]; this
0x14000a03e  call    ?IsTerminateNavigateUrl@AuthHostWebInstance@@AEAAJPEBG0PEAH@Z; AuthHostWebInstance::IsTerminateNavigateUrl(ushort const *,ushort const *,int *)
0x14000a043  mov     ebp, eax
0x14000a045  test    rdi, rdi
0x14000a048  jz      short loc_14000A07A
0x14000a04a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000a04e  inc     rax
0x14000a051  cmp     [rdi+rax*2], r12w
0x14000a056  jnz     short loc_14000A04E
0x14000a058  lea     rcx, [rax+rax]
0x14000a05c  mov     rax, rdi
0x14000a05f  test    rcx, rcx
0x14000a062  jz      short loc_14000A070
0x14000a064  mov     [rax], r12b
0x14000a067  inc     rax
0x14000a06a  sub     rcx, 1
0x14000a06e  jnz     short loc_14000A064
0x14000a070  mov     rcx, rdi; hMem
0x14000a073  call    cs:__imp_LocalFree
0x14000a079  nop
0x14000a07a  mov     rcx, [rsp+68h+bstrString]; bstrString
0x14000a082  call    cs:__imp_SysFreeString
0x14000a088  mov     eax, ebp
0x14000a08a  mov     rbx, [rsp+68h+arg_0]
0x14000a08f  mov     rbp, [rsp+68h+arg_8]
0x14000a094  add     rsp, 40h
0x14000a098  pop     r15
0x14000a09a  pop     r14
0x14000a09c  pop     r12
0x14000a09e  pop     rdi
0x14000a09f  pop     rsi
0x14000a0a0  retn
```
