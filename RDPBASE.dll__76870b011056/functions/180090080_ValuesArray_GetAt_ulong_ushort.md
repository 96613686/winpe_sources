# ValuesArray::GetAt(ulong,ushort * *)

- ea: `0x180090080`
- end: `0x1800902b7`
- name: `?GetAt@ValuesArray@@UEAAJKPEAPEAG@Z`
- size: `567`
- prototype: `__int64 __fastcall(ValuesArray *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callees

- `0x180038984`
- `0x1800711c8`
- `0x180071a60`
- `0x1800721d4`
- `0x1800787d4`
- `0x180078820`
- `0x180090080`
- `0x1800923f8`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090107`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800902a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090107`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800902a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009019c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009019c`

## string_xrefs

- `0x18009015e`: `m_spJsonArray->GetStringAt failed!`
- `0x180090261`: `StringCchCopy failed!`

## pseudocode

```c
__int64 __fastcall ValuesArray::GetAt(ValuesArray *this, __int64 a2, unsigned __int16 **a3)
{
  unsigned int v4; // ebp
  unsigned int v5; // eax
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax
  const unsigned __int16 *StringRawBuffer; // rbx
  unsigned __int16 *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned __int16 *v16; // rdi
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  int ActivityIdPrefix; // eax
  UINT32 length; // [rsp+60h] [rbp+18h] BYREF
  HSTRING string; // [rsp+68h] [rbp+20h] BYREF

  string = 0;
  length = 0;
  v4 = a2;
  if ( a3 )
  {
    v7 = *((_QWORD *)this + 7);
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v7 + 64LL);
    WindowsDeleteString(0);
    string = 0;
    v6 = v8(v7, v4, &string);
    if ( v6 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
      v13 = (unsigned __int16 *)operator new(saturated_mul(++length, 2u));
      v16 = v13;
      if ( v13 )
      {
        v6 = StringCchCopyW(v13, length, StringRawBuffer);
        if ( v6 >= 0 )
        {
          *a3 = v16;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v18, v19);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
              ActivityIdPrefix,
              (__int64)"StringCchCopy failed!",
              v6);
          }
          operator delete(v16);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v17 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v14, v15);
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
            v17,
            (__int64)"WCHAR[]");
        }
        v6 = -2147024882;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v9, v10);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
        v11,
        (__int64)"m_spJsonArray->GetStringAt failed!",
        v6);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, a2, 0);
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
        v5,
        -2147024809);
    }
    v6 = -2147024809;
  }
  WindowsDeleteString(string);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180090080  mov     [rsp+arg_0], rbx
0x180090085  push    rbp
0x180090086  push    rsi
0x180090087  push    rdi
0x180090088  sub     rsp, 30h
0x18009008c  mov     [rsp+48h+string], 0
0x180090095  mov     rsi, r8
0x180090098  mov     [rsp+48h+length], 0
0x1800900a0  mov     ebp, edx
0x1800900a2  test    r8, r8
0x1800900a5  jnz     short loc_1800900FA
0x1800900a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800900ae  lea     rax, WPP_GLOBAL_Control
0x1800900b5  cmp     rcx, rax
0x1800900b8  jz      short loc_1800900F0
0x1800900ba  test    byte ptr [rcx+1Ch], 8
0x1800900be  jz      short loc_1800900F0
0x1800900c0  cmp     byte ptr [rcx+19h], 2
0x1800900c4  jb      short loc_1800900F0
0x1800900c6  call    RdpX_GetActivityIdPrefix
0x1800900cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800900d2  lea     edx, [rsi+0Dh]
0x1800900d5  mov     r9d, eax
0x1800900d8  mov     dword ptr [rsp+48h+var_28], 80070057h
0x1800900e0  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x1800900e7  mov     rcx, [rcx+10h]
0x1800900eb  call    WPP_SF_Dd
0x1800900f0  mov     ebx, 80070057h
0x1800900f5  jmp     loc_18009029D
0x1800900fa  mov     rdi, [rcx+38h]
0x1800900fe  xor     ecx, ecx; string
0x180090100  mov     rax, [rdi]
0x180090103  mov     rbx, [rax+40h]
0x180090107  call    cs:__imp_WindowsDeleteString
0x18009010d  lea     r8, [rsp+48h+string]
0x180090112  mov     [rsp+48h+string], 0
0x18009011b  mov     edx, ebp
0x18009011d  mov     rcx, rdi
0x180090120  mov     rax, rbx
0x180090123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090128  mov     ebx, eax
0x18009012a  test    eax, eax
0x18009012c  jns     short loc_180090192
0x18009012e  mov     rcx, cs:WPP_GLOBAL_Control
0x180090135  lea     rax, WPP_GLOBAL_Control
0x18009013c  cmp     rcx, rax
0x18009013f  jz      loc_18009029D
0x180090145  test    byte ptr [rcx+1Ch], 8
0x180090149  jz      loc_18009029D
0x18009014f  cmp     byte ptr [rcx+19h], 2
0x180090153  jb      loc_18009029D
0x180090159  call    RdpX_GetActivityIdPrefix
0x18009015e  lea     rcx, aMSpjsonarrayGe; "m_spJsonArray->GetStringAt failed!"
0x180090165  mov     [rsp+48h+var_20], ebx
0x180090169  mov     [rsp+48h+var_28], rcx
0x18009016e  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180090175  mov     rcx, cs:WPP_GLOBAL_Control
0x18009017c  mov     edx, 0Eh
0x180090181  mov     r9d, eax
0x180090184  mov     rcx, [rcx+10h]
0x180090188  call    WPP_SF_DsD
0x18009018d  jmp     loc_18009029D
0x180090192  mov     rcx, [rsp+48h+string]; string
0x180090197  lea     rdx, [rsp+48h+length]; length
0x18009019c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800901a2  mov     ecx, [rsp+48h+length]
0x1800901a6  mov     rbx, rax
0x1800901a9  inc     ecx
0x1800901ab  mov     eax, 2
0x1800901b0  mov     edx, ecx
0x1800901b2  mov     [rsp+48h+length], ecx
0x1800901b6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800901bd  mul     rdx
0x1800901c0  cmovb   rax, rcx
0x1800901c4  mov     rcx, rax; Size
0x1800901c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800901cc  mov     rdi, rax
0x1800901cf  test    rax, rax
0x1800901d2  jnz     short loc_180090228
0x1800901d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800901db  lea     rax, WPP_GLOBAL_Control
0x1800901e2  cmp     rcx, rax
0x1800901e5  jz      short loc_180090221
0x1800901e7  test    byte ptr [rcx+1Ch], 8
0x1800901eb  jz      short loc_180090221
0x1800901ed  cmp     byte ptr [rcx+19h], 2
0x1800901f1  jb      short loc_180090221
0x1800901f3  call    RdpX_GetActivityIdPrefix
0x1800901f8  lea     rcx, aWchar; "WCHAR[]"
0x1800901ff  mov     r9d, eax
0x180090202  mov     [rsp+48h+var_28], rcx
0x180090207  lea     edx, [rdi+0Fh]
0x18009020a  mov     rcx, cs:WPP_GLOBAL_Control
0x180090211  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180090218  mov     rcx, [rcx+10h]
0x18009021c  call    WPP_SF_Ds
0x180090221  mov     ebx, 8007000Eh
0x180090226  jmp     short loc_18009029D
0x180090228  mov     edx, [rsp+48h+length]; unsigned __int64
0x18009022c  mov     r8, rbx; unsigned __int16 *
0x18009022f  mov     rcx, rdi; unsigned __int16 *
0x180090232  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180090237  mov     ebx, eax
0x180090239  test    eax, eax
0x18009023b  jns     short loc_18009029A
0x18009023d  mov     rcx, cs:WPP_GLOBAL_Control
0x180090244  lea     rax, WPP_GLOBAL_Control
0x18009024b  cmp     rcx, rax
0x18009024e  jz      short loc_180090290
0x180090250  test    byte ptr [rcx+1Ch], 8
0x180090254  jz      short loc_180090290
0x180090256  cmp     byte ptr [rcx+19h], 2
0x18009025a  jb      short loc_180090290
0x18009025c  call    RdpX_GetActivityIdPrefix
0x180090261  lea     rcx, aStringcchcopyF; "StringCchCopy failed!"
0x180090268  mov     [rsp+48h+var_20], ebx
0x18009026c  mov     [rsp+48h+var_28], rcx
0x180090271  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180090278  mov     rcx, cs:WPP_GLOBAL_Control
0x18009027f  mov     edx, 10h
0x180090284  mov     r9d, eax
0x180090287  mov     rcx, [rcx+10h]
0x18009028b  call    WPP_SF_DsD
0x180090290  mov     rcx, rdi; Block
0x180090293  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180090298  jmp     short loc_18009029D
0x18009029a  mov     [rsi], rdi
0x18009029d  mov     rcx, [rsp+48h+string]; string
0x1800902a2  call    cs:__imp_WindowsDeleteString
0x1800902a8  mov     eax, ebx
0x1800902aa  mov     rbx, [rsp+48h+arg_0]
0x1800902af  add     rsp, 30h
0x1800902b3  pop     rdi
0x1800902b4  pop     rsi
0x1800902b5  pop     rbp
0x1800902b6  retn
```
