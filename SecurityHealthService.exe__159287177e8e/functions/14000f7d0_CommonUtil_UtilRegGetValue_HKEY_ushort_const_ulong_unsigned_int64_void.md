# CommonUtil::UtilRegGetValue(HKEY__ *,ushort const *,ulong *,unsigned __int64 *,void *)

- ea: `0x14000f7d0`
- end: `0x14000f8e9`
- name: `?UtilRegGetValue@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAKPEA_KPEAX@Z`
- size: `281`
- prototype: `__int64 __fastcall(CommonUtil *this, const WCHAR *, DWORD *, unsigned int *, BYTE *lpData)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f8f0`
- `0x14000fab4`

## callees

- `0x1400071c0`
- `0x14000f7d0`
- `0x14000ff50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000f822`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000f822`

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
0x14000f7d0  push    rbx
0x14000f7d2  push    rbp
0x14000f7d3  push    rsi
0x14000f7d4  push    rdi
0x14000f7d5  push    r14
0x14000f7d7  push    r15
0x14000f7d9  sub     rsp, 38h
0x14000f7dd  mov     r14, [r9]
0x14000f7e0  mov     rdi, r9
0x14000f7e3  mov     eax, r14d
0x14000f7e6  mov     r15, r8
0x14000f7e9  mov     [rsp+68h+cbData], eax
0x14000f7f0  mov     rsi, rdx
0x14000f7f3  cmp     rax, r14
0x14000f7f6  jz      short loc_14000F802
0x14000f7f8  mov     eax, 80070057h
0x14000f7fd  jmp     loc_14000F8DC
0x14000f802  mov     rbp, [rsp+68h+arg_20]
0x14000f80a  lea     rax, [rsp+68h+cbData]
0x14000f812  mov     [rsp+68h+lpcbData], rax; lpcbData
0x14000f817  mov     r9, r15; lpType
0x14000f81a  xor     r8d, r8d; lpReserved
0x14000f81d  mov     [rsp+68h+lpData], rbp; lpData
0x14000f822  call    cs:__imp_RegQueryValueExW
0x14000f828  mov     ebx, eax
0x14000f82a  test    eax, eax
0x14000f82c  jle     short loc_14000F837
0x14000f82e  movzx   ebx, ax
0x14000f831  or      ebx, 80070000h
0x14000f837  test    ebx, ebx
0x14000f839  js      short loc_14000F87B
0x14000f83b  test    rbp, rbp
0x14000f83e  jz      short loc_14000F859
0x14000f840  mov     eax, [rsp+68h+cbData]
0x14000f847  cmp     rax, [rdi]
0x14000f84a  jbe     short loc_14000F859
0x14000f84c  mov     [rdi], rax
0x14000f84f  mov     eax, 800700EAh
0x14000f854  jmp     loc_14000F8DC
0x14000f859  mov     eax, [rsp+68h+cbData]
0x14000f860  mov     r9, rdi
0x14000f863  mov     r8d, [r15]
0x14000f866  mov     rdx, r14
0x14000f869  mov     rcx, rsi
0x14000f86c  mov     [rdi], rax
0x14000f86f  mov     [rsp+68h+lpData], rbp
0x14000f874  call    CommonUtil__UtilRegPostGetValue
0x14000f879  jmp     short loc_14000F8DC
0x14000f87b  mov     eax, 80070002h
0x14000f880  cmp     ebx, eax
0x14000f882  jz      short loc_14000F8DC
0x14000f884  mov     eax, 800700EAh
0x14000f889  cmp     ebx, eax
0x14000f88b  jz      short loc_14000F8C6
0x14000f88d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f894  lea     rax, WPP_GLOBAL_Control
0x14000f89b  cmp     rcx, rax
0x14000f89e  jz      short loc_14000F8C2
0x14000f8a0  test    byte ptr [rcx+1Ch], 1
0x14000f8a4  jz      short loc_14000F8C2
0x14000f8a6  mov     rcx, [rcx+10h]
0x14000f8aa  lea     r8, WPP_473dbbf2212f33a3d422106396b3062c_Traceguids
0x14000f8b1  mov     edx, 15h
0x14000f8b6  mov     dword ptr [rsp+68h+lpData], ebx
0x14000f8ba  mov     r9, rsi
0x14000f8bd  call    WPP_SF_Sd
0x14000f8c2  mov     eax, ebx
0x14000f8c4  jmp     short loc_14000F8DC
0x14000f8c6  mov     ecx, [rsp+68h+cbData]
0x14000f8cd  cmp     [rdi], rcx
0x14000f8d0  jb      short loc_14000F8D9
0x14000f8d2  mov     eax, 8000FFFFh
0x14000f8d7  jmp     short loc_14000F8DC
0x14000f8d9  mov     [rdi], rcx
0x14000f8dc  add     rsp, 38h
0x14000f8e0  pop     r15
0x14000f8e2  pop     r14
0x14000f8e4  pop     rdi
0x14000f8e5  pop     rsi
0x14000f8e6  pop     rbp
0x14000f8e7  pop     rbx
0x14000f8e8  retn
```
