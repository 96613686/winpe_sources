# Windows::UI::Input::InjectionBrokerImpl::InjectPenInput(unsigned __int64,Windows::UI::Input::PointerPenInfo const *)

- ea: `0x180006d00`
- end: `0x180006dbb`
- name: `?InjectPenInput@InjectionBrokerImpl@Input@UI@Windows@@UEAAJ_KPEBUPointerPenInfo@234@@Z`
- size: `187`
- prototype: `__int64 __fastcall(Windows::UI::Input::InjectionBrokerImpl *this, __int64, const struct Windows::UI::Input::PointerPenInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006d00`
- `0x18001143a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d98`
- `ext-ms-win-ntuser-rim-l1-1-0!InjectPointerInput` at `0x180006d8e`
- `ext-ms-win-ntuser-rim-l1-1-0!InjectPointerInput` at `0x180006d8e`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::InjectionBrokerImpl::InjectPenInput(
        Windows::UI::Input::InjectionBrokerImpl *this,
        __int64 a2,
        const struct Windows::UI::Input::PointerPenInfo *a3)
{
  unsigned int v5; // esi
  signed int LastError; // eax
  _DWORD v8[22]; // [rsp+20h] [rbp-69h] BYREF
  __int64 v9; // [rsp+78h] [rbp-11h]
  int v10; // [rsp+88h] [rbp-1h]
  int v11; // [rsp+8Ch] [rbp+3h]
  int v12; // [rsp+90h] [rbp+7h]
  int v13; // [rsp+94h] [rbp+Bh]
  int v14; // [rsp+98h] [rbp+Fh]
  int v15; // [rsp+9Ch] [rbp+13h]

  v5 = 0;
  memset_0(v8, 0, 0x98u);
  v10 = *((_DWORD *)a3 + 10);
  v11 = *((_DWORD *)a3 + 11);
  v8[3] = *((_DWORD *)a3 + 1);
  v8[4] = *((_DWORD *)a3 + 2);
  v8[5] = *((_DWORD *)a3 + 3);
  v8[10] = *((_DWORD *)a3 + 4);
  v8[11] = *((_DWORD *)a3 + 5);
  v8[18] = *((_DWORD *)a3 + 6);
  v9 = *((_QWORD *)a3 + 4);
  v12 = *((_DWORD *)a3 + 12);
  v13 = *((_DWORD *)a3 + 13);
  v14 = *((_DWORD *)a3 + 14);
  v15 = *((_DWORD *)a3 + 15);
  v8[2] = 3;
  v8[0] = 3;
  if ( !(unsigned int)InjectPointerInput(a2, v8, 1) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v5;
}

```

## disassembly

```asm
0x180006d00  push    rbp
0x180006d02  push    rbx
0x180006d03  push    rsi
0x180006d04  push    rdi
0x180006d05  lea     rbp, [rsp-3Fh]
0x180006d0a  sub     rsp, 0C8h
0x180006d11  mov     rbx, r8
0x180006d14  lea     rcx, [rbp+57h+var_C0]; void *
0x180006d18  mov     rdi, rdx
0x180006d1b  mov     r8d, 98h; Size
0x180006d21  xor     edx, edx; Val
0x180006d23  xor     esi, esi
0x180006d25  call    memset_0
0x180006d2a  mov     eax, [rbx+28h]
0x180006d2d  lea     r8d, [rsi+1]
0x180006d31  mov     [rbp+57h+var_58], eax
0x180006d34  lea     rdx, [rbp+57h+var_C0]
0x180006d38  mov     eax, [rbx+2Ch]
0x180006d3b  mov     rcx, rdi
0x180006d3e  mov     [rbp+57h+var_54], eax
0x180006d41  mov     eax, [rbx+4]
0x180006d44  mov     [rbp+57h+var_B4], eax
0x180006d47  mov     eax, [rbx+8]
0x180006d4a  mov     [rbp+57h+var_B0], eax
0x180006d4d  mov     eax, [rbx+0Ch]
0x180006d50  mov     [rbp+57h+var_AC], eax
0x180006d53  mov     eax, [rbx+10h]
0x180006d56  mov     [rbp+57h+var_98], eax
0x180006d59  mov     eax, [rbx+14h]
0x180006d5c  mov     [rbp+57h+var_94], eax
0x180006d5f  mov     eax, [rbx+18h]
0x180006d62  mov     [rbp+57h+var_78], eax
0x180006d65  mov     rax, [rbx+20h]
0x180006d69  mov     [rbp+57h+var_68], rax
0x180006d6d  mov     eax, [rbx+30h]
0x180006d70  mov     [rbp+57h+var_50], eax
0x180006d73  mov     eax, [rbx+34h]
0x180006d76  mov     [rbp+57h+var_4C], eax
0x180006d79  mov     eax, [rbx+38h]
0x180006d7c  mov     [rbp+57h+var_48], eax
0x180006d7f  mov     eax, [rbx+3Ch]
0x180006d82  mov     [rbp+57h+var_44], eax
0x180006d85  lea     eax, [rsi+3]
0x180006d88  mov     [rbp+57h+var_B8], eax
0x180006d8b  mov     [rbp+57h+var_C0], eax
0x180006d8e  call    cs:__imp_InjectPointerInput
0x180006d94  test    eax, eax
0x180006d96  jnz     short loc_180006DAD
0x180006d98  call    cs:__imp_GetLastError
0x180006d9e  mov     esi, eax
0x180006da0  test    eax, eax
0x180006da2  jle     short loc_180006DAD
0x180006da4  movzx   esi, ax
0x180006da7  or      esi, 80070000h
0x180006dad  mov     eax, esi
0x180006daf  add     rsp, 0C8h
0x180006db6  pop     rdi
0x180006db7  pop     rsi
0x180006db8  pop     rbx
0x180006db9  pop     rbp
0x180006dba  retn
```
