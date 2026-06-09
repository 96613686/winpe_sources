# _GetWindowTitle

- ea: `0x14000be88`
- end: `0x14000bf70`
- name: `_GetWindowTitle`
- size: `232`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400096cc`
- `0x140009988`
- `0x14000c2dc`

## callees

- `0x140003a8c`
- `0x14000b7d4`
- `0x14000be88`
- `0x140014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000bf51`
- `OLEAUT32!__imp_SysFreeString` at `0x14000bf51`
- `OLEAUT32!__imp_SysStringLen` at `0x14000bf0c`
- `OLEAUT32!__imp_SysStringLen` at `0x14000bf0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetWindowTitle(__int64 a1, BSTR *a2)
{
  int v4; // ebx
  OLECHAR *v5; // rcx
  __int64 (__fastcall *v6)(__int64, __int64 *); // rbx
  UINT v7; // eax
  int v8; // eax
  unsigned __int64 v9; // rdx
  BSTR v10; // rax
  BSTR pbstr; // [rsp+40h] [rbp+20h] BYREF
  __int64 v13; // [rsp+48h] [rbp+28h] BYREF
  unsigned __int64 v14; // [rsp+50h] [rbp+30h] BYREF

  v4 = -2146893807;
  v13 = 0;
  v5 = 0;
  pbstr = 0;
  v14 = 0;
  *a2 = 0;
  if ( a1 )
  {
    v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 416LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    v4 = v6(a1, &v13);
    if ( v4 < 0 )
    {
      v5 = pbstr;
      goto LABEL_12;
    }
    if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v13 + 136LL))(v13, &pbstr) >= 0 )
    {
      v5 = pbstr;
      if ( !pbstr )
      {
LABEL_10:
        v4 = -2146893807;
        goto LABEL_12;
      }
      v7 = SysStringLen(pbstr);
      v8 = StringCchLengthW(pbstr, v7 + 1, &v14);
      v9 = v14;
      v5 = 0;
      if ( v8 < 0 )
        v9 = 0;
      if ( v9 )
      {
        v4 = 0;
        v10 = pbstr;
        pbstr = 0;
        *a2 = v10;
        goto LABEL_12;
      }
    }
    v5 = pbstr;
    goto LABEL_10;
  }
LABEL_12:
  SysFreeString(v5);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000be88  mov     [rsp-18h+arg_18], rbx
0x14000be8d  push    rbp
0x14000be8e  push    rsi
0x14000be8f  push    rdi
0x14000be90  mov     rbp, rsp
0x14000be93  sub     rsp, 20h
0x14000be97  mov     rsi, rdx
0x14000be9a  mov     rdi, rcx
0x14000be9d  mov     ebx, 80090011h
0x14000bea2  mov     [rbp+arg_8], 0
0x14000beaa  xor     ecx, ecx
0x14000beac  mov     [rbp+pbstr], rcx
0x14000beb0  mov     [rbp+arg_10], rcx
0x14000beb4  mov     [rdx], rcx
0x14000beb7  test    rdi, rdi
0x14000beba  jz      loc_14000BF51
0x14000bec0  mov     rax, [rdi]
0x14000bec3  mov     rbx, [rax+1A0h]
0x14000beca  lea     rcx, [rbp+arg_8]
0x14000bece  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000bed3  lea     rdx, [rbp+arg_8]
0x14000bed7  mov     rcx, rdi
0x14000beda  mov     rax, rbx
0x14000bedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bee2  mov     ebx, eax
0x14000bee4  test    eax, eax
0x14000bee6  js      short loc_14000BF4D
0x14000bee8  mov     rcx, [rbp+arg_8]
0x14000beec  mov     rax, [rcx]
0x14000beef  lea     rdx, [rbp+pbstr]
0x14000bef3  mov     rax, [rax+88h]
0x14000befa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000beff  test    eax, eax
0x14000bf01  js      short loc_14000BF42
0x14000bf03  mov     rcx, [rbp+pbstr]; pbstr
0x14000bf07  test    rcx, rcx
0x14000bf0a  jz      short loc_14000BF46
0x14000bf0c  call    cs:__imp_SysStringLen
0x14000bf12  lea     edx, [rax+1]; unsigned __int64
0x14000bf15  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x14000bf19  mov     rcx, [rbp+pbstr]; unsigned __int16 *
0x14000bf1d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14000bf22  mov     rdx, [rbp+arg_10]
0x14000bf26  xor     ecx, ecx
0x14000bf28  test    eax, eax
0x14000bf2a  cmovs   rdx, rcx
0x14000bf2e  test    rdx, rdx
0x14000bf31  jz      short loc_14000BF42
0x14000bf33  xor     ebx, ebx
0x14000bf35  mov     rax, [rbp+pbstr]
0x14000bf39  mov     [rbp+pbstr], rcx
0x14000bf3d  mov     [rsi], rax
0x14000bf40  jmp     short loc_14000BF51
0x14000bf42  mov     rcx, [rbp+pbstr]
0x14000bf46  mov     ebx, 80090011h
0x14000bf4b  jmp     short loc_14000BF51
0x14000bf4d  mov     rcx, [rbp+pbstr]; bstrString
0x14000bf51  call    cs:__imp_SysFreeString
0x14000bf57  nop
0x14000bf58  lea     rcx, [rbp+arg_8]
0x14000bf5c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000bf61  mov     eax, ebx
0x14000bf63  mov     rbx, [rsp+20h+arg_18]
0x14000bf68  add     rsp, 20h
0x14000bf6c  pop     rdi
0x14000bf6d  pop     rsi
0x14000bf6e  pop     rbp
0x14000bf6f  retn
```
