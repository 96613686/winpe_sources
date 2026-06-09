# CommonUtil::HrGetModuleFileName(unsigned __int64 *,ushort *,HINSTANCE__ *)

- ea: `0x180006e04`
- end: `0x180006ea9`
- name: `?HrGetModuleFileName@CommonUtil@@YAJPEA_KPEAGPEAUHINSTANCE__@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned __int64 *, unsigned __int16 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006f68`

## callees

- `0x180004b7c`
- `0x180006e04`
- `0x1800090e4`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180006e2c`
- `KERNEL32!GetModuleFileNameW` at `0x180006e2c`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrGetModuleFileName(CommonUtil *this, WCHAR *a2, unsigned __int16 *a3, HINSTANCE a4)
{
  __int64 v4; // rbx
  __int64 result; // rax
  DWORD ModuleFileNameW; // eax
  DWORD v9; // ecx
  unsigned int LastFailure; // ebx

  v4 = *(unsigned int *)this;
  if ( v4 != *(_QWORD *)this )
    return 2147942487LL;
  if ( !(_DWORD)v4 )
    return 2147942522LL;
  ModuleFileNameW = GetModuleFileNameW(0, a2, v4);
  v9 = ModuleFileNameW;
  if ( ModuleFileNameW )
  {
    if ( ModuleFileNameW >= (unsigned int)v4 )
    {
      result = 2147942522LL;
      if ( v9 != (_DWORD)v4 )
        return 2147549183LL;
    }
    else if ( a2[ModuleFileNameW] )
    {
      return 2147549183LL;
    }
    else
    {
      *(_QWORD *)this = ModuleFileNameW + 1;
      return 0;
    }
  }
  else
  {
    LastFailure = HrGetLastFailure(0);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_e2b92b5a14063cae8af40d4f75517e75_Traceguids, LastFailure);
    return LastFailure;
  }
  return result;
}

```

## disassembly

```asm
0x180006e04  push    rbx
0x180006e06  push    rbp
0x180006e07  push    rsi
0x180006e08  push    rdi
0x180006e09  sub     rsp, 28h
0x180006e0d  mov     ebx, [rcx]
0x180006e0f  mov     rsi, rdx
0x180006e12  mov     rdi, rcx
0x180006e15  cmp     rbx, [rcx]
0x180006e18  jz      short loc_180006E21
0x180006e1a  mov     eax, 80070057h
0x180006e1f  jmp     short loc_180006EA0
0x180006e21  xor     ebp, ebp
0x180006e23  test    ebx, ebx
0x180006e25  jz      short loc_180006E9B
0x180006e27  mov     r8d, ebx; nSize
0x180006e2a  xor     ecx, ecx; hModule
0x180006e2c  call    cs:__imp_GetModuleFileNameW
0x180006e32  mov     ecx, eax
0x180006e34  test    eax, eax
0x180006e36  jnz     short loc_180006E72
0x180006e38  call    HrGetLastFailure
0x180006e3d  mov     ebx, eax
0x180006e3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e46  lea     rax, WPP_GLOBAL_Control
0x180006e4d  cmp     rcx, rax
0x180006e50  jz      short loc_180006E6E
0x180006e52  test    byte ptr [rcx+1Ch], 1
0x180006e56  jz      short loc_180006E6E
0x180006e58  mov     rcx, [rcx+10h]
0x180006e5c  lea     edx, [rbp+20h]
0x180006e5f  mov     r9d, ebx
0x180006e62  lea     r8, WPP_e2b92b5a14063cae8af40d4f75517e75_Traceguids
0x180006e69  call    WPP_SF_d
0x180006e6e  mov     eax, ebx
0x180006e70  jmp     short loc_180006EA0
0x180006e72  cmp     ecx, ebx
0x180006e74  jnb     short loc_180006E8C
0x180006e76  cmp     [rsi+rcx*2], bp
0x180006e7a  jnz     short loc_180006E85
0x180006e7c  inc     ecx
0x180006e7e  mov     [rdi], rcx
0x180006e81  xor     eax, eax
0x180006e83  jmp     short loc_180006EA0
0x180006e85  mov     eax, 8000FFFFh
0x180006e8a  jmp     short loc_180006EA0
0x180006e8c  mov     eax, 8007007Ah
0x180006e91  mov     edx, 8000FFFFh
0x180006e96  cmovnz  eax, edx
0x180006e99  jmp     short loc_180006EA0
0x180006e9b  mov     eax, 8007007Ah
0x180006ea0  add     rsp, 28h
0x180006ea4  pop     rdi
0x180006ea5  pop     rsi
0x180006ea6  pop     rbp
0x180006ea7  pop     rbx
0x180006ea8  retn
```
