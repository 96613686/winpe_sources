# AuthHostWebInstance::OnBeforeNavigateRefresh(IHTMLWindow2 *,IUri *,WebPlatformRefresh,WebPlatformNavigationDataFlags,int *)

- ea: `0x14000a0b0`
- end: `0x14000a1ff`
- name: `?OnBeforeNavigateRefresh@AuthHostWebInstance@@UEAAJPEAUIHTMLWindow2@@PEAUIUri@@W4WebPlatformRefresh@@W4WebPlatformNavigationDataFlags@@PEAH@Z`
- size: `335`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140002c98`
- `0x14000a0b0`
- `0x14000cca0`
- `0x140014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000a1e2`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a1e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AuthHostWebInstance::OnBeforeNavigateRefresh(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        __int64 a5,
        __int64 a6)
{
  int v10; // eax
  unsigned int v11; // ebx
  BSTR bstrString; // [rsp+A0h] [rbp+18h] BYREF

  bstrString = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a3 + 56LL))(a3, &bstrString);
  v11 = v10;
  if ( v10 >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        27,
        (unsigned int)&WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids,
        (_DWORD)bstrString,
        a4);
    }
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, __int64))(*(_QWORD *)a1 + 32LL))(
            a1,
            a2,
            a3,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            a6);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      26,
      &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids,
      (unsigned int)v10);
  }
  SysFreeString(bstrString);
  return v11;
}

```

## disassembly

```asm
0x14000a0b0  mov     r11, rsp
0x14000a0b3  mov     [r11+8], rbx
0x14000a0b7  mov     [r11+10h], rbp
0x14000a0bb  push    rsi
0x14000a0bc  push    rdi
0x14000a0bd  push    r14
0x14000a0bf  sub     rsp, 70h
0x14000a0c3  mov     ebp, r9d
0x14000a0c6  mov     rdi, r8
0x14000a0c9  mov     r14, rdx
0x14000a0cc  mov     rsi, rcx
0x14000a0cf  mov     qword ptr [r11+18h], 0
0x14000a0d7  mov     rax, [r8]
0x14000a0da  lea     rdx, [r11+18h]
0x14000a0de  mov     rcx, r8
0x14000a0e1  mov     rax, [rax+38h]
0x14000a0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0ea  mov     ebx, eax
0x14000a0ec  test    eax, eax
0x14000a0ee  jns     short loc_14000A138
0x14000a0f0  lea     rdx, WPP_GLOBAL_Control
0x14000a0f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a0fe  cmp     rcx, rdx
0x14000a101  jz      loc_14000A1DA
0x14000a107  test    byte ptr [rcx+44h], 4
0x14000a10b  jz      loc_14000A1DA
0x14000a111  cmp     byte ptr [rcx+41h], 5
0x14000a115  jb      loc_14000A1DA
0x14000a11b  mov     edx, 1Ah
0x14000a120  mov     r9d, eax
0x14000a123  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000a12a  mov     rcx, [rcx+38h]
0x14000a12e  call    WPP_SF_d
0x14000a133  jmp     loc_14000A1DA
0x14000a138  lea     rdx, WPP_GLOBAL_Control
0x14000a13f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a146  cmp     rcx, rdx
0x14000a149  jz      short loc_14000A178
0x14000a14b  test    byte ptr [rcx+44h], 4
0x14000a14f  jz      short loc_14000A178
0x14000a151  cmp     byte ptr [rcx+41h], 5
0x14000a155  jb      short loc_14000A178
0x14000a157  mov     edx, 1Bh
0x14000a15c  mov     [rsp+88h+var_68], ebp
0x14000a160  mov     r9, [rsp+88h+bstrString]
0x14000a168  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000a16f  mov     rcx, [rcx+38h]
0x14000a173  call    WPP_SF_Sd
0x14000a178  mov     rax, [rsi]
0x14000a17b  mov     rcx, [rsp+88h+arg_28]
0x14000a183  mov     [rsp+88h+var_30], rcx
0x14000a188  mov     [rsp+88h+var_38], 0
0x14000a190  mov     [rsp+88h+var_40], 0
0x14000a199  mov     [rsp+88h+var_48], 0
0x14000a1a1  mov     [rsp+88h+var_50], 0
0x14000a1aa  mov     [rsp+88h+var_58], 0
0x14000a1b3  mov     [rsp+88h+var_60], 0
0x14000a1bb  mov     [rsp+88h+var_68], 0
0x14000a1c3  xor     r9d, r9d
0x14000a1c6  mov     r8, rdi
0x14000a1c9  mov     rdx, r14
0x14000a1cc  mov     rcx, rsi
0x14000a1cf  mov     rax, [rax+20h]
0x14000a1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1d8  mov     ebx, eax
0x14000a1da  mov     rcx, [rsp+88h+bstrString]; bstrString
0x14000a1e2  call    cs:__imp_SysFreeString
0x14000a1e8  mov     eax, ebx
0x14000a1ea  lea     r11, [rsp+88h+var_18]
0x14000a1ef  mov     rbx, [r11+20h]
0x14000a1f3  mov     rbp, [r11+28h]
0x14000a1f7  mov     rsp, r11
0x14000a1fa  pop     r14
0x14000a1fc  pop     rdi
0x14000a1fd  pop     rsi
0x14000a1fe  retn
```
