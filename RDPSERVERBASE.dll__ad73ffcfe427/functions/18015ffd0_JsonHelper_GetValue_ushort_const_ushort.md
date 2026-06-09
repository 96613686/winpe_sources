# JsonHelper::GetValue(ushort const *,ushort * *)

- ea: `0x18015ffd0`
- end: `0x1801601d9`
- name: `?GetValue@JsonHelper@@UEAAJPEBGPEAPEAG@Z`
- size: `521`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18003b118`
- `0x180076090`
- `0x180077aa0`
- `0x18007e9e0`
- `0x18007f6a4`
- `0x18007f6b0`
- `0x18015ede4`
- `0x18015ffd0`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18016006f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180160106`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18016016f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18016006f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180160106`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18016016f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801600b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801600b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180160010`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801601b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180160010`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801601b5`

## string_xrefs

- `0x180160175`: `StringCchCopy failed!`
- `0x180160075`: `m_spJsonObj->GetNamedString failed!`

## pseudocode

```c
__int64 __fastcall JsonHelper::GetValue(JsonHelper *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v6; // rax
  __int64 v7; // rdx
  int v8; // ebx
  int v9; // eax
  const unsigned __int16 *StringRawBuffer; // rbx
  unsigned __int16 *v11; // rax
  __int64 v12; // rdx
  unsigned __int16 *v13; // rdi
  int v14; // eax
  __int64 v15; // rdx
  int ActivityIdPrefix; // eax
  UINT32 length; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  const unsigned __int16 *v20; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v21[32]; // [rsp+48h] [rbp-28h] BYREF

  v3 = *((_QWORD *)this + 7);
  string = 0;
  length = 0;
  v20 = a2;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v3 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v21, &v20);
  v8 = v5(v3, *(_QWORD *)(v6 + 24), &string);
  if ( v8 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v11 = (unsigned __int16 *)operator new(saturated_mul(++length, 2u));
    v13 = v11;
    if ( v11 )
    {
      v8 = StringCchCopyW(v11, length, StringRawBuffer);
      if ( v8 >= 0 )
      {
        *a3 = v13;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v15);
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
            ActivityIdPrefix,
            (__int64)"StringCchCopy failed!",
            v8);
        }
        operator delete(v13);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v12);
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
          v14,
          (__int64)"WCHAR[]");
      }
      v8 = -2147024882;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v7);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      v9,
      (__int64)"m_spJsonObj->GetNamedString failed!",
      v8);
  }
  WindowsDeleteString(string);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18015ffd0  mov     [rsp-18h+arg_18], rbx
0x18015ffd5  push    rbp
0x18015ffd6  push    rsi
0x18015ffd7  push    rdi
0x18015ffd8  mov     rbp, rsp
0x18015ffdb  sub     rsp, 70h
0x18015ffdf  mov     rax, cs:__security_cookie
0x18015ffe6  xor     rax, rsp
0x18015ffe9  mov     [rbp+var_8], rax
0x18015ffed  mov     rdi, [rcx+38h]
0x18015fff1  mov     rsi, r8
0x18015fff4  mov     [rbp+string], 0
0x18015fffc  xor     ecx, ecx; string
0x18015fffe  mov     [rbp+length], 0
0x180160005  mov     [rbp+var_30], rdx
0x180160009  mov     rax, [rdi]
0x18016000c  mov     rbx, [rax+50h]
0x180160010  call    cs:__imp_WindowsDeleteString
0x180160016  lea     rdx, [rbp+var_30]
0x18016001a  mov     [rbp+string], 0
0x180160022  lea     rcx, [rbp+var_28]
0x180160026  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18016002b  lea     r8, [rbp+string]
0x18016002f  mov     rcx, rdi
0x180160032  mov     rdx, [rax+18h]
0x180160036  mov     rax, rbx
0x180160039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016003e  mov     ebx, eax
0x180160040  test    eax, eax
0x180160042  jns     short loc_1801600A9
0x180160044  mov     rax, cs:WPP_GLOBAL_Control
0x18016004b  lea     rcx, WPP_GLOBAL_Control
0x180160052  cmp     rax, rcx
0x180160055  jz      loc_1801601B1
0x18016005b  test    byte ptr [rax+1Ch], 8
0x18016005f  jz      loc_1801601B1
0x180160065  cmp     byte ptr [rax+19h], 2
0x180160069  jb      loc_1801601B1
0x18016006f  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180160075  lea     rcx, aMSpjsonobjGetn; "m_spJsonObj->GetNamedString failed!"
0x18016007c  mov     [rsp+70h+var_48], ebx
0x180160080  mov     [rsp+70h+var_50], rcx
0x180160085  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18016008c  mov     rcx, cs:WPP_GLOBAL_Control
0x180160093  mov     edx, 22h ; '"'
0x180160098  mov     r9d, eax
0x18016009b  mov     rcx, [rcx+10h]
0x18016009f  call    WPP_SF_DsD
0x1801600a4  jmp     loc_1801601B1
0x1801600a9  mov     rcx, [rbp+string]; string
0x1801600ad  lea     rdx, [rbp+length]; length
0x1801600b1  call    cs:__imp_WindowsGetStringRawBuffer
0x1801600b7  mov     ecx, [rbp+length]
0x1801600ba  mov     rbx, rax
0x1801600bd  inc     ecx
0x1801600bf  mov     eax, 2
0x1801600c4  mov     edx, ecx
0x1801600c6  mov     [rbp+length], ecx
0x1801600c9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1801600d0  mul     rdx
0x1801600d3  cmovb   rax, rcx
0x1801600d7  mov     rcx, rax; Size
0x1801600da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801600df  mov     rdi, rax
0x1801600e2  test    rax, rax
0x1801600e5  jnz     short loc_18016013C
0x1801600e7  mov     rax, cs:WPP_GLOBAL_Control
0x1801600ee  lea     rcx, WPP_GLOBAL_Control
0x1801600f5  cmp     rax, rcx
0x1801600f8  jz      short loc_180160135
0x1801600fa  test    byte ptr [rax+1Ch], 8
0x1801600fe  jz      short loc_180160135
0x180160100  cmp     byte ptr [rax+19h], 2
0x180160104  jb      short loc_180160135
0x180160106  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18016010c  lea     rcx, aWchar_0; "WCHAR[]"
0x180160113  mov     r9d, eax
0x180160116  mov     [rsp+70h+var_50], rcx
0x18016011b  lea     edx, [rdi+23h]
0x18016011e  mov     rcx, cs:WPP_GLOBAL_Control
0x180160125  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18016012c  mov     rcx, [rcx+10h]
0x180160130  call    WPP_SF_Ds
0x180160135  mov     ebx, 8007000Eh
0x18016013a  jmp     short loc_1801601B1
0x18016013c  mov     edx, [rbp+length]; unsigned __int64
0x18016013f  mov     r8, rbx; unsigned __int16 *
0x180160142  mov     rcx, rdi; unsigned __int16 *
0x180160145  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18016014a  mov     ebx, eax
0x18016014c  test    eax, eax
0x18016014e  jns     short loc_1801601AE
0x180160150  mov     rax, cs:WPP_GLOBAL_Control
0x180160157  lea     rcx, WPP_GLOBAL_Control
0x18016015e  cmp     rax, rcx
0x180160161  jz      short loc_1801601A4
0x180160163  test    byte ptr [rax+1Ch], 8
0x180160167  jz      short loc_1801601A4
0x180160169  cmp     byte ptr [rax+19h], 2
0x18016016d  jb      short loc_1801601A4
0x18016016f  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180160175  lea     rcx, aStringcchcopyF; "StringCchCopy failed!"
0x18016017c  mov     [rsp+70h+var_48], ebx
0x180160180  mov     [rsp+70h+var_50], rcx
0x180160185  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18016018c  mov     rcx, cs:WPP_GLOBAL_Control
0x180160193  mov     edx, 24h ; '$'
0x180160198  mov     r9d, eax
0x18016019b  mov     rcx, [rcx+10h]
0x18016019f  call    WPP_SF_DsD
0x1801601a4  mov     rcx, rdi; Block
0x1801601a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801601ac  jmp     short loc_1801601B1
0x1801601ae  mov     [rsi], rdi
0x1801601b1  mov     rcx, [rbp+string]; string
0x1801601b5  call    cs:__imp_WindowsDeleteString
0x1801601bb  mov     eax, ebx
0x1801601bd  mov     rcx, [rbp+var_8]
0x1801601c1  xor     rcx, rsp; StackCookie
0x1801601c4  call    __security_check_cookie
0x1801601c9  mov     rbx, [rsp+70h+arg_18]
0x1801601d1  add     rsp, 70h
0x1801601d5  pop     rdi
0x1801601d6  pop     rsi
0x1801601d7  pop     rbp
0x1801601d8  retn
```
