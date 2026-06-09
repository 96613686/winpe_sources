# AuthHostWebInstance::OnDocumentComplete(IHTMLWindow2 *,IUri *,WebPlatformNavigationDataFlags)

- ea: `0x14000a330`
- end: `0x14000a4a6`
- name: `?OnDocumentComplete@AuthHostWebInstance@@UEAAJPEAUIHTMLWindow2@@PEAUIUri@@W4WebPlatformNavigationDataFlags@@@Z`
- size: `374`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140002c98`
- `0x14000429c`
- `0x14000a330`
- `0x14000c0c0`
- `0x14000c2dc`
- `0x14000c3dc`
- `0x140014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000a495`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a495`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AuthHostWebInstance::OnDocumentComplete(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // eax
  unsigned int v6; // esi
  const wchar_t *v7; // rdi
  __int64 v8; // rcx
  BSTR bstrString; // [rsp+60h] [rbp+18h] BYREF

  bstrString = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a3 + 56LL))(a3, &bstrString);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = bstrString;
    if ( (unsigned __int8)IsValidWindow(a2) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 33, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids, v7);
      }
      TraceWindow(a2);
      v8 = *(unsigned int *)(a1 + 124);
      if ( (((_DWORD)v8 - 1) & 0xFFFFFFFC) == 0 && (_DWORD)v8 != 3 )
      {
        if ( (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(v8, (const EVENT_DESCRIPTOR *)DocumentCompleteEvent, v7);
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 96) + 96LL))(*(_QWORD *)(a1 + 96), 4);
      }
      if ( *(_DWORD *)(a1 + 124) == 1 )
        *(_DWORD *)(a1 + 124) = 2;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 32, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids, v7);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      31,
      &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids,
      (unsigned int)v5);
  }
  SysFreeString(bstrString);
  return v6;
}

```

## disassembly

```asm
0x14000a330  push    rbx
0x14000a332  push    rbp
0x14000a333  push    rsi
0x14000a334  push    rdi
0x14000a335  sub     rsp, 28h
0x14000a339  mov     rbp, rdx
0x14000a33c  mov     rbx, rcx
0x14000a33f  mov     [rsp+48h+bstrString], 0
0x14000a348  mov     rax, [r8]
0x14000a34b  lea     rdx, [rsp+48h+bstrString]
0x14000a350  mov     rcx, r8
0x14000a353  mov     rax, [rax+38h]
0x14000a357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a35c  mov     esi, eax
0x14000a35e  test    eax, eax
0x14000a360  jns     short loc_14000A3AC
0x14000a362  lea     rcx, WPP_GLOBAL_Control
0x14000a369  mov     r10, cs:WPP_GLOBAL_Control
0x14000a370  cmp     r10, rcx
0x14000a373  jz      loc_14000A490
0x14000a379  test    byte ptr [r10+44h], 4
0x14000a37e  jz      loc_14000A490
0x14000a384  cmp     byte ptr [r10+41h], 5
0x14000a389  jb      loc_14000A490
0x14000a38f  mov     edx, 1Fh
0x14000a394  mov     r9d, eax
0x14000a397  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000a39e  mov     rcx, [r10+38h]
0x14000a3a2  call    WPP_SF_d
0x14000a3a7  jmp     loc_14000A490
0x14000a3ac  mov     rdi, [rsp+48h+bstrString]
0x14000a3b1  mov     rcx, rbp
0x14000a3b4  call    _IsValidWindow
0x14000a3b9  test    al, al
0x14000a3bb  jnz     short loc_14000A405
0x14000a3bd  lea     rcx, WPP_GLOBAL_Control
0x14000a3c4  mov     rax, cs:WPP_GLOBAL_Control
0x14000a3cb  cmp     rax, rcx
0x14000a3ce  jz      loc_14000A490
0x14000a3d4  test    byte ptr [rax+44h], 4
0x14000a3d8  jz      loc_14000A490
0x14000a3de  cmp     byte ptr [rax+41h], 5
0x14000a3e2  jb      loc_14000A490
0x14000a3e8  mov     edx, 20h ; ' '
0x14000a3ed  mov     r9, rdi
0x14000a3f0  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000a3f7  mov     rcx, [rax+38h]
0x14000a3fb  call    WPP_SF_S
0x14000a400  jmp     loc_14000A490
0x14000a405  lea     rcx, WPP_GLOBAL_Control
0x14000a40c  mov     rax, cs:WPP_GLOBAL_Control
0x14000a413  cmp     rax, rcx
0x14000a416  jz      short loc_14000A43C
0x14000a418  test    byte ptr [rax+44h], 4
0x14000a41c  jz      short loc_14000A43C
0x14000a41e  cmp     byte ptr [rax+41h], 5
0x14000a422  jb      short loc_14000A43C
0x14000a424  mov     edx, 21h ; '!'
0x14000a429  mov     r9, rdi
0x14000a42c  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000a433  mov     rcx, [rax+38h]
0x14000a437  call    WPP_SF_S
0x14000a43c  mov     rcx, rbp
0x14000a43f  call    _TraceWindow
0x14000a444  mov     ecx, [rbx+7Ch]
0x14000a447  lea     eax, [rcx-1]
0x14000a44a  test    eax, 0FFFFFFFCh
0x14000a44f  jnz     short loc_14000A483
0x14000a451  cmp     ecx, 3
0x14000a454  jz      short loc_14000A483
0x14000a456  test    cs:Microsoft_Windows_WebAuthEnableBits, 1
0x14000a45d  jz      short loc_14000A46E
0x14000a45f  mov     r8, rdi
0x14000a462  lea     rdx, DocumentCompleteEvent
0x14000a469  call    McTemplateU0z_EventWriteTransfer
0x14000a46e  mov     rcx, [rbx+60h]
0x14000a472  mov     rax, [rcx]
0x14000a475  mov     edx, 4
0x14000a47a  mov     rax, [rax+60h]
0x14000a47e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a483  cmp     dword ptr [rbx+7Ch], 1
0x14000a487  jnz     short loc_14000A490
0x14000a489  mov     dword ptr [rbx+7Ch], 2
0x14000a490  mov     rcx, [rsp+48h+bstrString]; bstrString
0x14000a495  call    cs:__imp_SysFreeString
0x14000a49b  mov     eax, esi
0x14000a49d  add     rsp, 28h
0x14000a4a1  pop     rdi
0x14000a4a2  pop     rsi
0x14000a4a3  pop     rbp
0x14000a4a4  pop     rbx
0x14000a4a5  retn
```
