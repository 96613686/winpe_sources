# AuthHostWebInstance::OnNavigateRedirected(IHTMLWindow2 *,IUri *,IUri *,ulong,WebPlatformNavigationDataFlags,int *)

- ea: `0x14000abe0`
- end: `0x14000ad7a`
- name: `?OnNavigateRedirected@AuthHostWebInstance@@UEAAJPEAUIHTMLWindow2@@PEAUIUri@@1KW4WebPlatformNavigationDataFlags@@PEAH@Z`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140002c98`
- `0x1400097b0`
- `0x14000abe0`
- `0x14000c2dc`
- `0x14000c598`
- `0x14000c7c4`
- `0x140014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000ad53`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ad5f`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ad53`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ad5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AuthHostWebInstance::OnNavigateRedirected(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int IsTerminateNavigateUrl; // ebx
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rcx
  int v15; // esi
  const unsigned __int16 *v16; // rbx
  char v17; // di
  int v18; // edx
  int v19; // ecx
  BSTR v21[5]; // [rsp+40h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+18h] BYREF

  v21[0] = 0;
  bstrString = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a3 + 56LL))(a3, v21);
  IsTerminateNavigateUrl = v10;
  if ( v10 >= 0 )
  {
    IsTerminateNavigateUrl = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a4 + 56LL))(a4, &bstrString);
    if ( IsTerminateNavigateUrl >= 0 )
    {
      v15 = (int)v21[0];
      v16 = bstrString;
      v17 = a5;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
      {
        WPP_SF_DdSS(*((_QWORD *)WPP_GLOBAL_Control + 7), a5, (__int64)bstrString, (__int64)v21[0]);
      }
      TraceWindow(a2);
      if ( (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
        McTemplateU0zzq_EventWriteTransfer(v19, v18, (_DWORD)v16, v15, v17);
      IsTerminateNavigateUrl = AuthHostWebInstance::IsTerminateNavigateUrl((AuthHostWebInstance *)(a1 - 8), v16, 0, a7);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      v12 = 44;
      v13 = (unsigned int)IsTerminateNavigateUrl;
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 7);
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    v12 = 43;
    v13 = (unsigned int)v10;
    v14 = *((_QWORD *)WPP_GLOBAL_Control + 7);
LABEL_6:
    WPP_SF_d(v14, v12, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids, v13);
  }
  SysFreeString(bstrString);
  SysFreeString(v21[0]);
  return (unsigned int)IsTerminateNavigateUrl;
}

```

## disassembly

```asm
0x14000abe0  mov     r11, rsp
0x14000abe3  mov     [r11+8], rbx
0x14000abe7  mov     [r11+10h], rbp
0x14000abeb  push    rsi
0x14000abec  push    rdi
0x14000abed  push    r14
0x14000abef  sub     rsp, 50h
0x14000abf3  mov     rdi, r9
0x14000abf6  mov     rbp, rdx
0x14000abf9  mov     r14, rcx
0x14000abfc  mov     qword ptr [r11-28h], 0
0x14000ac04  mov     qword ptr [r11+18h], 0
0x14000ac0c  mov     rax, [r8]
0x14000ac0f  lea     rdx, [r11-28h]
0x14000ac13  mov     rcx, r8
0x14000ac16  mov     rax, [rax+38h]
0x14000ac1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac1f  mov     ebx, eax
0x14000ac21  test    eax, eax
0x14000ac23  jns     short loc_14000AC6F
0x14000ac25  lea     rcx, WPP_GLOBAL_Control
0x14000ac2c  mov     r10, cs:WPP_GLOBAL_Control
0x14000ac33  cmp     r10, rcx
0x14000ac36  jz      loc_14000AD4B
0x14000ac3c  test    byte ptr [r10+44h], 4
0x14000ac41  jz      loc_14000AD4B
0x14000ac47  cmp     byte ptr [r10+41h], 5
0x14000ac4c  jb      loc_14000AD4B
0x14000ac52  mov     edx, 2Bh ; '+'
0x14000ac57  mov     r9d, eax
0x14000ac5a  mov     rcx, [r10+38h]
0x14000ac5e  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000ac65  call    WPP_SF_d
0x14000ac6a  jmp     loc_14000AD4B
0x14000ac6f  mov     rax, [rdi]
0x14000ac72  lea     rdx, [rsp+68h+bstrString]
0x14000ac7a  mov     rcx, rdi
0x14000ac7d  mov     rax, [rax+38h]
0x14000ac81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac86  mov     ebx, eax
0x14000ac88  test    eax, eax
0x14000ac8a  jns     short loc_14000ACC5
0x14000ac8c  lea     rcx, WPP_GLOBAL_Control
0x14000ac93  mov     rax, cs:WPP_GLOBAL_Control
0x14000ac9a  cmp     rax, rcx
0x14000ac9d  jz      loc_14000AD4B
0x14000aca3  test    byte ptr [rax+44h], 4
0x14000aca7  jz      loc_14000AD4B
0x14000acad  cmp     byte ptr [rax+41h], 5
0x14000acb1  jb      loc_14000AD4B
0x14000acb7  mov     edx, 2Ch ; ','
0x14000acbc  mov     r9d, ebx
0x14000acbf  mov     rcx, [rax+38h]
0x14000acc3  jmp     short loc_14000AC5E
0x14000acc5  mov     rsi, [rsp+68h+var_28]
0x14000acca  mov     rbx, [rsp+68h+bstrString]
0x14000acd2  lea     rcx, WPP_GLOBAL_Control
0x14000acd9  mov     edi, dword ptr [rsp+68h+arg_20]
0x14000ace0  mov     rax, cs:WPP_GLOBAL_Control
0x14000ace7  cmp     rax, rcx
0x14000acea  jz      short loc_14000AD12
0x14000acec  test    byte ptr [rax+44h], 4
0x14000acf0  jz      short loc_14000AD12
0x14000acf2  cmp     byte ptr [rax+41h], 5
0x14000acf6  jb      short loc_14000AD12
0x14000acf8  mov     [rsp+68h+var_38], rsi; __int64
0x14000acfd  mov     [rsp+68h+var_40], rbx; __int64
0x14000ad02  mov     dword ptr [rsp+68h+var_48], edi; char
0x14000ad06  mov     r9d, edi
0x14000ad09  mov     rcx, [rax+38h]; LoggerHandle
0x14000ad0d  call    WPP_SF_DdSS
0x14000ad12  mov     rcx, rbp
0x14000ad15  call    _TraceWindow
0x14000ad1a  test    cs:Microsoft_Windows_WebAuthEnableBits, 1
0x14000ad21  jz      short loc_14000AD32
0x14000ad23  mov     dword ptr [rsp+68h+var_48], edi
0x14000ad27  mov     r9, rsi
0x14000ad2a  mov     r8, rbx
0x14000ad2d  call    McTemplateU0zzq_EventWriteTransfer
0x14000ad32  lea     rcx, [r14-8]; this
0x14000ad36  mov     r9, [rsp+68h+arg_30]; int *
0x14000ad3e  xor     r8d, r8d; unsigned __int16 *
0x14000ad41  mov     rdx, rbx; unsigned __int16 *
0x14000ad44  call    ?IsTerminateNavigateUrl@AuthHostWebInstance@@AEAAJPEBG0PEAH@Z; AuthHostWebInstance::IsTerminateNavigateUrl(ushort const *,ushort const *,int *)
0x14000ad49  mov     ebx, eax
0x14000ad4b  mov     rcx, [rsp+68h+bstrString]; bstrString
0x14000ad53  call    cs:__imp_SysFreeString
0x14000ad59  nop
0x14000ad5a  mov     rcx, [rsp+68h+var_28]; bstrString
0x14000ad5f  call    cs:__imp_SysFreeString
0x14000ad65  mov     eax, ebx
0x14000ad67  mov     rbx, [rsp+68h+arg_0]
0x14000ad6c  mov     rbp, [rsp+68h+arg_8]
0x14000ad71  add     rsp, 50h
0x14000ad75  pop     r14
0x14000ad77  pop     rdi
0x14000ad78  pop     rsi
0x14000ad79  retn
```
