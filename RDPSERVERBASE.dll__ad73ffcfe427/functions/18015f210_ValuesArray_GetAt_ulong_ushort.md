# ValuesArray::GetAt(ulong,ushort * *)

- ea: `0x18015f210`
- end: `0x18015f44b`
- name: `?GetAt@ValuesArray@@UEAAJKPEAPEAG@Z`
- size: `571`
- prototype: `__int64 __fastcall(ValuesArray *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x18003b118`
- `0x180076090`
- `0x180077aa0`
- `0x180079724`
- `0x18007f6a4`
- `0x18007f6b0`
- `0x18015f210`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f256`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f2ea`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f385`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f3ef`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f256`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f2ea`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f385`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18015f3ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015f32e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015f32e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015f298`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015f436`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015f298`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015f436`

## string_xrefs

- `0x18015f2f0`: `m_spJsonArray->GetStringAt failed!`
- `0x18015f3f5`: `StringCchCopy failed!`

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
  int v10; // eax
  const unsigned __int16 *StringRawBuffer; // rbx
  unsigned __int16 *v12; // rax
  __int64 v13; // rdx
  unsigned __int16 *v14; // rdi
  int v15; // eax
  __int64 v16; // rdx
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
      v12 = (unsigned __int16 *)operator new(saturated_mul(++length, 2u));
      v14 = v12;
      if ( v12 )
      {
        v6 = StringCchCopyW(v12, length, StringRawBuffer);
        if ( v6 >= 0 )
        {
          *a3 = v14;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v16);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
              ActivityIdPrefix,
              (__int64)"StringCchCopy failed!",
              v6);
          }
          operator delete(v14);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v13);
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
            v15,
            (__int64)"WCHAR[]");
        }
        v6 = -2147024882;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v9);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
        v10,
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
      v5 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, a2);
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
0x18015f210  mov     [rsp+arg_0], rbx
0x18015f215  push    rbp
0x18015f216  push    rsi
0x18015f217  push    rdi
0x18015f218  sub     rsp, 30h
0x18015f21c  mov     [rsp+48h+string], 0
0x18015f225  mov     rsi, r8
0x18015f228  mov     [rsp+48h+length], 0
0x18015f230  mov     ebp, edx
0x18015f232  test    r8, r8
0x18015f235  jnz     short loc_18015F28B
0x18015f237  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f23e  lea     rax, WPP_GLOBAL_Control
0x18015f245  cmp     rcx, rax
0x18015f248  jz      short loc_18015F281
0x18015f24a  test    byte ptr [rcx+1Ch], 8
0x18015f24e  jz      short loc_18015F281
0x18015f250  cmp     byte ptr [rcx+19h], 2
0x18015f254  jb      short loc_18015F281
0x18015f256  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18015f25c  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f263  lea     edx, [rsi+0Dh]
0x18015f266  mov     r9d, eax
0x18015f269  mov     dword ptr [rsp+48h+var_28], 80070057h
0x18015f271  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18015f278  mov     rcx, [rcx+10h]
0x18015f27c  call    WPP_SF_Dd
0x18015f281  mov     ebx, 80070057h
0x18015f286  jmp     loc_18015F431
0x18015f28b  mov     rdi, [rcx+38h]
0x18015f28f  xor     ecx, ecx; string
0x18015f291  mov     rax, [rdi]
0x18015f294  mov     rbx, [rax+40h]
0x18015f298  call    cs:__imp_WindowsDeleteString
0x18015f29e  lea     r8, [rsp+48h+string]
0x18015f2a3  mov     [rsp+48h+string], 0
0x18015f2ac  mov     edx, ebp
0x18015f2ae  mov     rcx, rdi
0x18015f2b1  mov     rax, rbx
0x18015f2b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015f2b9  mov     ebx, eax
0x18015f2bb  test    eax, eax
0x18015f2bd  jns     short loc_18015F324
0x18015f2bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f2c6  lea     rax, WPP_GLOBAL_Control
0x18015f2cd  cmp     rcx, rax
0x18015f2d0  jz      loc_18015F431
0x18015f2d6  test    byte ptr [rcx+1Ch], 8
0x18015f2da  jz      loc_18015F431
0x18015f2e0  cmp     byte ptr [rcx+19h], 2
0x18015f2e4  jb      loc_18015F431
0x18015f2ea  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18015f2f0  lea     rcx, aMSpjsonarrayGe; "m_spJsonArray->GetStringAt failed!"
0x18015f2f7  mov     [rsp+48h+var_20], ebx
0x18015f2fb  mov     [rsp+48h+var_28], rcx
0x18015f300  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18015f307  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f30e  mov     edx, 0Eh
0x18015f313  mov     r9d, eax
0x18015f316  mov     rcx, [rcx+10h]
0x18015f31a  call    WPP_SF_DsD
0x18015f31f  jmp     loc_18015F431
0x18015f324  mov     rcx, [rsp+48h+string]; string
0x18015f329  lea     rdx, [rsp+48h+length]; length
0x18015f32e  call    cs:__imp_WindowsGetStringRawBuffer
0x18015f334  mov     ecx, [rsp+48h+length]
0x18015f338  mov     rbx, rax
0x18015f33b  inc     ecx
0x18015f33d  mov     eax, 2
0x18015f342  mov     edx, ecx
0x18015f344  mov     [rsp+48h+length], ecx
0x18015f348  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18015f34f  mul     rdx
0x18015f352  cmovb   rax, rcx
0x18015f356  mov     rcx, rax; Size
0x18015f359  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18015f35e  mov     rdi, rax
0x18015f361  test    rax, rax
0x18015f364  jnz     short loc_18015F3BB
0x18015f366  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f36d  lea     rax, WPP_GLOBAL_Control
0x18015f374  cmp     rcx, rax
0x18015f377  jz      short loc_18015F3B4
0x18015f379  test    byte ptr [rcx+1Ch], 8
0x18015f37d  jz      short loc_18015F3B4
0x18015f37f  cmp     byte ptr [rcx+19h], 2
0x18015f383  jb      short loc_18015F3B4
0x18015f385  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18015f38b  lea     rcx, aWchar_0; "WCHAR[]"
0x18015f392  mov     r9d, eax
0x18015f395  mov     [rsp+48h+var_28], rcx
0x18015f39a  lea     edx, [rdi+0Fh]
0x18015f39d  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f3a4  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18015f3ab  mov     rcx, [rcx+10h]
0x18015f3af  call    WPP_SF_Ds
0x18015f3b4  mov     ebx, 8007000Eh
0x18015f3b9  jmp     short loc_18015F431
0x18015f3bb  mov     edx, [rsp+48h+length]; unsigned __int64
0x18015f3bf  mov     r8, rbx; unsigned __int16 *
0x18015f3c2  mov     rcx, rdi; unsigned __int16 *
0x18015f3c5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18015f3ca  mov     ebx, eax
0x18015f3cc  test    eax, eax
0x18015f3ce  jns     short loc_18015F42E
0x18015f3d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f3d7  lea     rax, WPP_GLOBAL_Control
0x18015f3de  cmp     rcx, rax
0x18015f3e1  jz      short loc_18015F424
0x18015f3e3  test    byte ptr [rcx+1Ch], 8
0x18015f3e7  jz      short loc_18015F424
0x18015f3e9  cmp     byte ptr [rcx+19h], 2
0x18015f3ed  jb      short loc_18015F424
0x18015f3ef  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18015f3f5  lea     rcx, aStringcchcopyF; "StringCchCopy failed!"
0x18015f3fc  mov     [rsp+48h+var_20], ebx
0x18015f400  mov     [rsp+48h+var_28], rcx
0x18015f405  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18015f40c  mov     rcx, cs:WPP_GLOBAL_Control
0x18015f413  mov     edx, 10h
0x18015f418  mov     r9d, eax
0x18015f41b  mov     rcx, [rcx+10h]
0x18015f41f  call    WPP_SF_DsD
0x18015f424  mov     rcx, rdi; Block
0x18015f427  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18015f42c  jmp     short loc_18015F431
0x18015f42e  mov     [rsi], rdi
0x18015f431  mov     rcx, [rsp+48h+string]; string
0x18015f436  call    cs:__imp_WindowsDeleteString
0x18015f43c  mov     eax, ebx
0x18015f43e  mov     rbx, [rsp+48h+arg_0]
0x18015f443  add     rsp, 30h
0x18015f447  pop     rdi
0x18015f448  pop     rsi
0x18015f449  pop     rbp
0x18015f44a  retn
```
