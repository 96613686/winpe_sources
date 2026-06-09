# CommonUtil::UtilRegGetValue(HKEY__ *,ushort const *,ulong *,unsigned __int64 *,void *)

- ea: `0x14000e35c`
- end: `0x14000e475`
- name: `?UtilRegGetValue@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAKPEA_KPEAX@Z`
- size: `281`
- prototype: `__int64 __fastcall(CommonUtil *this, const WCHAR *, DWORD *, unsigned int *, BYTE *lpData)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e47c`
- `0x14000e648`

## callees

- `0x14000dba8`
- `0x14000e35c`
- `0x14000ea64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000e3ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000e3ae`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegGetValue(
        CommonUtil *this,
        const WCHAR *a2,
        DWORD *a3,
        unsigned int *a4,
        BYTE *lpData)
{
  __int64 v5; // r14
  __int64 result; // rax
  BYTE *v10; // rbp
  LSTATUS v11; // eax
  signed int v12; // ebx
  __int64 v13; // r8
  DWORD cbData; // [rsp+88h] [rbp+20h] BYREF

  v5 = *(_QWORD *)a4;
  cbData = *(_QWORD *)a4;
  if ( cbData != v5 )
    return 2147942487LL;
  v10 = lpData;
  v11 = RegQueryValueExW((HKEY)this, a2, 0, a3, lpData, &cbData);
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( v12 < 0 )
  {
    result = 2147942402LL;
    if ( v12 != -2147024894 )
    {
      result = 2147942634LL;
      if ( v12 == -2147024662 )
      {
        if ( *(_QWORD *)a4 < (unsigned __int64)cbData )
          *(_QWORD *)a4 = cbData;
        else
          return 2147549183LL;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)&WPP_473dbbf2212f33a3d422106396b3062c_Traceguids,
            (_DWORD)a2,
            v12);
        return (unsigned int)v12;
      }
    }
  }
  else if ( v10 && (unsigned __int64)cbData > *(_QWORD *)a4 )
  {
    *(_QWORD *)a4 = cbData;
    return 2147942634LL;
  }
  else
  {
    v13 = *a3;
    *(_QWORD *)a4 = cbData;
    return CommonUtil::UtilRegPostGetValue(a2, v5, v13, a4, v10);
  }
  return result;
}

```

## disassembly

```asm
0x14000e35c  push    rbx
0x14000e35e  push    rbp
0x14000e35f  push    rsi
0x14000e360  push    rdi
0x14000e361  push    r14
0x14000e363  push    r15
0x14000e365  sub     rsp, 38h
0x14000e369  mov     r14, [r9]
0x14000e36c  mov     rdi, r9
0x14000e36f  mov     eax, r14d
0x14000e372  mov     r15, r8
0x14000e375  mov     [rsp+68h+cbData], eax
0x14000e37c  mov     rsi, rdx
0x14000e37f  cmp     rax, r14
0x14000e382  jz      short loc_14000E38E
0x14000e384  mov     eax, 80070057h
0x14000e389  jmp     loc_14000E468
0x14000e38e  mov     rbp, [rsp+68h+arg_20]
0x14000e396  lea     rax, [rsp+68h+cbData]
0x14000e39e  mov     [rsp+68h+lpcbData], rax; lpcbData
0x14000e3a3  mov     r9, r15; lpType
0x14000e3a6  xor     r8d, r8d; lpReserved
0x14000e3a9  mov     [rsp+68h+lpData], rbp; lpData
0x14000e3ae  call    cs:__imp_RegQueryValueExW
0x14000e3b4  mov     ebx, eax
0x14000e3b6  test    eax, eax
0x14000e3b8  jle     short loc_14000E3C3
0x14000e3ba  movzx   ebx, ax
0x14000e3bd  or      ebx, 80070000h
0x14000e3c3  test    ebx, ebx
0x14000e3c5  js      short loc_14000E407
0x14000e3c7  test    rbp, rbp
0x14000e3ca  jz      short loc_14000E3E5
0x14000e3cc  mov     eax, [rsp+68h+cbData]
0x14000e3d3  cmp     rax, [rdi]
0x14000e3d6  jbe     short loc_14000E3E5
0x14000e3d8  mov     [rdi], rax
0x14000e3db  mov     eax, 800700EAh
0x14000e3e0  jmp     loc_14000E468
0x14000e3e5  mov     eax, [rsp+68h+cbData]
0x14000e3ec  mov     r9, rdi
0x14000e3ef  mov     r8d, [r15]
0x14000e3f2  mov     rdx, r14
0x14000e3f5  mov     rcx, rsi
0x14000e3f8  mov     [rdi], rax
0x14000e3fb  mov     [rsp+68h+lpData], rbp
0x14000e400  call    CommonUtil__UtilRegPostGetValue
0x14000e405  jmp     short loc_14000E468
0x14000e407  mov     eax, 80070002h
0x14000e40c  cmp     ebx, eax
0x14000e40e  jz      short loc_14000E468
0x14000e410  mov     eax, 800700EAh
0x14000e415  cmp     ebx, eax
0x14000e417  jz      short loc_14000E452
0x14000e419  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e420  lea     rax, WPP_GLOBAL_Control
0x14000e427  cmp     rcx, rax
0x14000e42a  jz      short loc_14000E44E
0x14000e42c  test    byte ptr [rcx+1Ch], 1
0x14000e430  jz      short loc_14000E44E
0x14000e432  mov     rcx, [rcx+10h]
0x14000e436  lea     r8, WPP_473dbbf2212f33a3d422106396b3062c_Traceguids
0x14000e43d  mov     edx, 15h
0x14000e442  mov     dword ptr [rsp+68h+lpData], ebx
0x14000e446  mov     r9, rsi
0x14000e449  call    WPP_SF_Sd
0x14000e44e  mov     eax, ebx
0x14000e450  jmp     short loc_14000E468
0x14000e452  mov     ecx, [rsp+68h+cbData]
0x14000e459  cmp     [rdi], rcx
0x14000e45c  jb      short loc_14000E465
0x14000e45e  mov     eax, 8000FFFFh
0x14000e463  jmp     short loc_14000E468
0x14000e465  mov     [rdi], rcx
0x14000e468  add     rsp, 38h
0x14000e46c  pop     r15
0x14000e46e  pop     r14
0x14000e470  pop     rdi
0x14000e471  pop     rsi
0x14000e472  pop     rbp
0x14000e473  pop     rbx
0x14000e474  retn
```
