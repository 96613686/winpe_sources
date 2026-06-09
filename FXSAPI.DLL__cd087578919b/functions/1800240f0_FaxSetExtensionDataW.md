# FaxSetExtensionDataW

- ea: `0x1800240f0`
- end: `0x1800242f7`
- name: `FaxSetExtensionDataW`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024030`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x1800240f0`
- `0x18002c31c`
- `0x18003d510`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180024253`
- `RPCRT4!NdrClientCall3` at `0x180024253`
- `KERNEL32!GetComputerNameW` at `0x1800241c0`
- `KERNEL32!GetComputerNameW` at `0x1800241c0`
- `KERNEL32!SetLastError` at `0x1800242c7`
- `KERNEL32!SetLastError` at `0x1800242c7`
- `KERNEL32!GetLastError` at `0x1800241d0`
- `KERNEL32!GetLastError` at `0x1800241d0`

## pseudocode

```c
__int64 __fastcall FaxSetExtensionDataW(__int64 a1, int a2, const OLECHAR *a3, __int64 a4, int a5)
{
  DWORD valid; // eax
  DWORD v10; // ecx
  DWORD LastError; // eax
  DWORD Pointer; // ebx
  _QWORD *v13; // rax
  CLIENT_CALL_RETURN v14; // rax
  DWORD nSize[2]; // [rsp+50h] [rbp-78h] BYREF
  CLIENT_CALL_RETURN v17; // [rsp+58h] [rbp-70h]
  WCHAR Buffer[16]; // [rsp+60h] [rbp-68h] BYREF

  nSize[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids);
  }
  if ( a3 && a4 && a5 )
  {
    if ( a1 && *(_DWORD *)a1 && !*(_DWORD *)(a1 + 16) )
    {
      valid = IsValidGUID(a3);
      if ( valid )
      {
        v10 = valid;
      }
      else
      {
        nSize[0] = 16;
        if ( GetComputerNameW(Buffer, nSize) )
        {
          v13 = *(_QWORD **)(a1 + 32);
          v17.Simple = 0;
          v14.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x32u, 0, *v13, Buffer, a2, a3, a4, a5).Pointer;
          Pointer = (DWORD)v14.Pointer;
          v17.Pointer = v14.Pointer;
          nSize[1] = (DWORD)v14.Pointer;
          if ( !LODWORD(v14.Pointer) )
            return 1;
        }
        else
        {
          LastError = GetLastError();
          Pointer = LastError;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              97,
              WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids,
              LastError);
          }
        }
        v10 = Pointer;
      }
    }
    else
    {
      v10 = 6;
    }
  }
  else
  {
    v10 = 87;
  }
  SetLastError(v10);
  return 0;
}

```

## disassembly

```asm
0x1800240f0  push    rbx
0x1800240f2  push    rsi
0x1800240f3  push    rdi
0x1800240f4  push    r12
0x1800240f6  push    r14
0x1800240f8  push    r15
0x1800240fa  sub     rsp, 98h
0x180024101  mov     rax, cs:__security_cookie
0x180024108  xor     rax, rsp
0x18002410b  mov     [rsp+0C8h+var_48], rax
0x180024113  mov     r14, r9
0x180024116  mov     rsi, r8
0x180024119  mov     r15d, edx
0x18002411c  mov     rbx, rcx
0x18002411f  mov     [rsp+0C8h+nSize], 0
0x180024127  lea     r12, WPP_GLOBAL_Control
0x18002412e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024135  cmp     rcx, r12
0x180024138  jz      short loc_18002415E
0x18002413a  test    dword ptr [rcx+1Ch], 1000h
0x180024141  jz      short loc_18002415E
0x180024143  cmp     byte ptr [rcx+19h], 5
0x180024147  jb      short loc_18002415E
0x180024149  mov     edx, 60h ; '`'
0x18002414e  lea     r8, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids
0x180024155  mov     rcx, [rcx+10h]
0x180024159  call    WPP_SF_
0x18002415e  test    rsi, rsi
0x180024161  jz      loc_1800242C2
0x180024167  test    r14, r14
0x18002416a  jz      loc_1800242C2
0x180024170  mov     edi, [rsp+0C8h+arg_20]
0x180024177  test    edi, edi
0x180024179  jz      loc_1800242C2
0x18002417f  test    rbx, rbx
0x180024182  jz      loc_1800242BB
0x180024188  cmp     dword ptr [rbx], 0
0x18002418b  jz      loc_1800242BB
0x180024191  cmp     dword ptr [rbx+10h], 0
0x180024195  jnz     loc_1800242BB
0x18002419b  mov     rcx, rsi; lpsz
0x18002419e  call    IsValidGUID
0x1800241a3  test    eax, eax
0x1800241a5  jz      short loc_1800241AE
0x1800241a7  mov     ecx, eax
0x1800241a9  jmp     loc_1800242C7
0x1800241ae  mov     [rsp+0C8h+nSize], 10h
0x1800241b6  lea     rdx, [rsp+0C8h+nSize]; nSize
0x1800241bb  lea     rcx, [rsp+0C8h+Buffer]; lpBuffer
0x1800241c0  call    cs:__imp_GetComputerNameW
0x1800241c7  nop     dword ptr [rax+rax+00h]
0x1800241cc  test    eax, eax
0x1800241ce  jnz     short loc_180024218
0x1800241d0  call    cs:__imp_GetLastError
0x1800241d7  nop     dword ptr [rax+rax+00h]
0x1800241dc  mov     ebx, eax
0x1800241de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800241e5  cmp     rcx, r12
0x1800241e8  jz      short loc_180024211
0x1800241ea  test    dword ptr [rcx+1Ch], 1000h
0x1800241f1  jz      short loc_180024211
0x1800241f3  cmp     byte ptr [rcx+19h], 2
0x1800241f7  jb      short loc_180024211
0x1800241f9  mov     edx, 61h ; 'a'
0x1800241fe  mov     r9d, eax
0x180024201  lea     r8, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids
0x180024208  mov     rcx, [rcx+10h]
0x18002420c  call    WPP_SF_d
0x180024211  mov     ecx, ebx
0x180024213  jmp     loc_1800242C7
0x180024218  mov     rax, [rbx+20h]
0x18002421c  mov     [rsp+0C8h+var_70], 0
0x180024225  mov     [rsp+0C8h+var_88], edi
0x180024229  mov     [rsp+0C8h+var_90], r14
0x18002422e  mov     [rsp+0C8h+var_98], rsi
0x180024233  mov     [rsp+0C8h+var_A0], r15d
0x180024238  lea     rcx, [rsp+0C8h+Buffer]
0x18002423d  mov     [rsp+0C8h+var_A8], rcx
0x180024242  mov     r9, [rax]
0x180024245  xor     r8d, r8d; pReturnValue
0x180024248  lea     edx, [r8+32h]; nProcNum
0x18002424c  lea     rcx, pProxyInfo; pProxyInfo
0x180024253  call    cs:__imp_NdrClientCall3
0x18002425a  nop     dword ptr [rax+rax+00h]
0x18002425f  mov     rbx, rax
0x180024262  mov     [rsp+0C8h+var_70], rax
0x180024267  mov     [rsp+0C8h+var_74], eax
0x18002426b  jmp     short loc_1800242AE
0x18002426d  mov     ebx, eax
0x18002426f  mov     [rsp+0C8h+var_74], eax
0x180024273  lea     rdx, WPP_GLOBAL_Control
0x18002427a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024281  cmp     rcx, rdx
0x180024284  jz      short loc_1800242AE
0x180024286  test    dword ptr [rcx+1Ch], 1000h
0x18002428d  jz      short loc_1800242AE
0x18002428f  cmp     byte ptr [rcx+19h], 2
0x180024293  jb      short loc_1800242AE
0x180024295  mov     edx, 62h ; 'b'
0x18002429a  mov     r9d, eax
0x18002429d  lea     r8, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids
0x1800242a4  mov     rcx, [rcx+10h]
0x1800242a8  call    WPP_SF_d
0x1800242ad  nop
0x1800242ae  test    ebx, ebx
0x1800242b0  jnz     loc_180024211
0x1800242b6  lea     eax, [rbx+1]
0x1800242b9  jmp     short loc_1800242D5
0x1800242bb  mov     ecx, 6
0x1800242c0  jmp     short loc_1800242C7
0x1800242c2  mov     ecx, 57h ; 'W'; dwErrCode
0x1800242c7  call    cs:__imp_SetLastError
0x1800242ce  nop     dword ptr [rax+rax+00h]
0x1800242d3  xor     eax, eax
0x1800242d5  mov     rcx, [rsp+0C8h+var_48]
0x1800242dd  xor     rcx, rsp; StackCookie
0x1800242e0  call    __security_check_cookie
0x1800242e5  add     rsp, 98h
0x1800242ec  pop     r15
0x1800242ee  pop     r14
0x1800242f0  pop     r12
0x1800242f2  pop     rdi
0x1800242f3  pop     rsi
0x1800242f4  pop     rbx
0x1800242f5  retn
```
