# ApplicationSpecificEndpointInfo::ReadKey(HKEY__ *,ushort const *,ushort * *)

- ea: `0x18002b724`
- end: `0x18002b83c`
- name: `?ReadKey@ApplicationSpecificEndpointInfo@@CAJPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `280`
- prototype: `LSTATUS __fastcall(HKEY hkey, LPCWSTR lpValue, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e37c`
- `0x18001a134`
- `0x1800463e8`

## callees

- `0x18000a384`
- `0x180012844`
- `0x18002b724`
- `0x18004620c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b820`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b820`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b76d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b7f3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b76d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b7f3`

## pseudocode

```c
LSTATUS __fastcall ApplicationSpecificEndpointInfo::ReadKey(HKEY hkey, LPCWSTR lpValue, unsigned __int16 **a3)
{
  LSTATUS result; // eax
  PVOID v7; // rbx
  unsigned int ValueW; // eax
  int v9; // edi
  int pdwType; // [rsp+20h] [rbp-38h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD pcbData; // [rsp+70h] [rbp+18h] BYREF
  PVOID pv; // [rsp+78h] [rbp+20h] BYREF

  *a3 = 0;
  pcbData = 0;
  result = RegGetValueW(hkey, 0, lpValue, 2u, 0, 0, &pcbData);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    pcbData += 2;
    wil::make_unique_cotaskmem_nothrow<unsigned short [0]>(&pv, pcbData);
    v7 = pv;
    if ( pv )
    {
      ValueW = RegGetValueW(hkey, 0, lpValue, 2u, 0, pv, &pcbData);
      if ( ValueW )
      {
        v9 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x288,
               (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
               (const char *)ValueW,
               pdwTypea);
        if ( v7 )
          CoTaskMemFree(v7);
        return v9;
      }
      else
      {
        *a3 = (unsigned __int16 *)v7;
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x286,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
        (const char *)0x8007000ELL,
        pdwType);
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b724  mov     r11, rsp
0x18002b727  mov     [r11+8], rbx
0x18002b72b  push    rbp
0x18002b72c  push    rsi
0x18002b72d  push    rdi
0x18002b72e  sub     rsp, 40h
0x18002b732  lea     rax, [r11+18h]
0x18002b736  mov     qword ptr [r8], 0
0x18002b73d  mov     [r11-28h], rax
0x18002b741  mov     rdi, r8
0x18002b744  mov     rsi, rdx
0x18002b747  mov     qword ptr [r11-30h], 0
0x18002b74f  mov     r8, rdx; lpValue
0x18002b752  mov     qword ptr [r11-38h], 0
0x18002b75a  mov     r9d, 2; dwFlags
0x18002b760  mov     [rsp+58h+arg_10], 0
0x18002b768  xor     edx, edx; lpSubKey
0x18002b76a  mov     rbp, rcx
0x18002b76d  call    cs:__imp_RegGetValueW
0x18002b773  test    eax, eax
0x18002b775  jz      short loc_18002B78A
0x18002b777  jle     loc_18002B82F
0x18002b77d  movzx   eax, ax
0x18002b780  or      eax, 80070000h
0x18002b785  jmp     loc_18002B82F
0x18002b78a  mov     eax, [rsp+58h+arg_10]
0x18002b78e  lea     rcx, [rsp+58h+pv]
0x18002b793  add     eax, 2
0x18002b796  mov     edx, eax
0x18002b798  mov     [rsp+58h+arg_10], eax
0x18002b79c  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<ushort [0]>(unsigned __int64)
0x18002b7a1  mov     rbx, [rsp+58h+pv]
0x18002b7a6  test    rbx, rbx
0x18002b7a9  jnz     short loc_18002B7CD
0x18002b7ab  mov     rcx, [rsp+58h]; this
0x18002b7b0  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18002b7b7  mov     ebx, 8007000Eh
0x18002b7bc  mov     edx, 286h; void *
0x18002b7c1  mov     r9d, ebx; char *
0x18002b7c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b7c9  mov     eax, ebx
0x18002b7cb  jmp     short loc_18002B82F
0x18002b7cd  lea     rax, [rsp+58h+arg_10]
0x18002b7d2  mov     r9d, 2; dwFlags
0x18002b7d8  mov     [rsp+58h+pcbData], rax; pcbData
0x18002b7dd  mov     r8, rsi; lpValue
0x18002b7e0  mov     [rsp+58h+pvData], rbx; pvData
0x18002b7e5  xor     edx, edx; lpSubKey
0x18002b7e7  mov     rcx, rbp; hkey
0x18002b7ea  mov     [rsp+58h+pdwType], 0; unsigned int
0x18002b7f3  call    cs:__imp_RegGetValueW
0x18002b7f9  test    eax, eax
0x18002b7fb  jz      short loc_18002B82A
0x18002b7fd  mov     rcx, [rsp+58h]; this
0x18002b802  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18002b809  mov     r9d, eax; char *
0x18002b80c  mov     edx, 288h; void *
0x18002b811  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b816  mov     edi, eax
0x18002b818  test    rbx, rbx
0x18002b81b  jz      short loc_18002B826
0x18002b81d  mov     rcx, rbx; pv
0x18002b820  call    cs:__imp_CoTaskMemFree
0x18002b826  mov     eax, edi
0x18002b828  jmp     short loc_18002B82F
0x18002b82a  mov     [rdi], rbx
0x18002b82d  xor     eax, eax
0x18002b82f  mov     rbx, [rsp+58h+arg_0]
0x18002b834  add     rsp, 40h
0x18002b838  pop     rdi
0x18002b839  pop     rsi
0x18002b83a  pop     rbp
0x18002b83b  retn
```
