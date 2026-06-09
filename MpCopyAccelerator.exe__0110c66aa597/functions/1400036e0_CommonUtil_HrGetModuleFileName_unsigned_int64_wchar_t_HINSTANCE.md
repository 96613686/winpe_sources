# CommonUtil::HrGetModuleFileName(unsigned __int64 *,wchar_t *,HINSTANCE__ *)

- ea: `0x1400036e0`
- end: `0x1400037a3`
- name: `?HrGetModuleFileName@CommonUtil@@YAJPEA_KPEA_WPEAUHINSTANCE__@@@Z`
- size: `195`
- prototype: `int(CommonUtil *__hidden this, unsigned __int64 *, wchar_t *, HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003a24`

## callees

- `0x1400036e0`
- `0x14000493c`
- `0x14001da70`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14000371a`
- `KERNEL32!GetModuleFileNameW` at `0x14000371a`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrGetModuleFileName(CommonUtil *this, WCHAR *a2, wchar_t *a3, HINSTANCE a4)
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
  ModuleFileNameW = GetModuleFileNameW((HMODULE)a3, a2, v4);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b1ecc9abb7cc30bcf0685ece08501d8e_Traceguids, LastFailure);
    return LastFailure;
  }
  return result;
}

```

## disassembly

```asm
0x1400036e0  mov     [rsp+arg_0], rbx
0x1400036e5  mov     [rsp+arg_8], rbp
0x1400036ea  mov     [rsp+arg_10], rsi
0x1400036ef  push    rdi
0x1400036f0  sub     rsp, 20h
0x1400036f4  mov     ebx, [rcx]
0x1400036f6  mov     rax, r8
0x1400036f9  mov     rsi, rdx
0x1400036fc  mov     rdi, rcx
0x1400036ff  cmp     rbx, [rcx]
0x140003702  jz      short loc_14000370E
0x140003704  mov     eax, 80070057h
0x140003709  jmp     loc_14000378E
0x14000370e  xor     ebp, ebp
0x140003710  test    ebx, ebx
0x140003712  jz      short loc_140003789
0x140003714  mov     r8d, ebx; nSize
0x140003717  mov     rcx, rax; hModule
0x14000371a  call    cs:__imp_GetModuleFileNameW
0x140003720  mov     ecx, eax
0x140003722  test    eax, eax
0x140003724  jnz     short loc_140003760
0x140003726  call    HrGetLastFailure
0x14000372b  mov     ebx, eax
0x14000372d  mov     rcx, cs:WPP_GLOBAL_Control
0x140003734  lea     rax, WPP_GLOBAL_Control
0x14000373b  cmp     rcx, rax
0x14000373e  jz      short loc_14000375C
0x140003740  test    byte ptr [rcx+1Ch], 1
0x140003744  jz      short loc_14000375C
0x140003746  mov     rcx, [rcx+10h]
0x14000374a  lea     edx, [rbp+13h]
0x14000374d  mov     r9d, ebx
0x140003750  lea     r8, WPP_b1ecc9abb7cc30bcf0685ece08501d8e_Traceguids
0x140003757  call    WPP_SF_d
0x14000375c  mov     eax, ebx
0x14000375e  jmp     short loc_14000378E
0x140003760  cmp     ecx, ebx
0x140003762  jnb     short loc_14000377A
0x140003764  cmp     [rsi+rcx*2], bp
0x140003768  jnz     short loc_140003773
0x14000376a  inc     ecx
0x14000376c  mov     [rdi], rcx
0x14000376f  xor     eax, eax
0x140003771  jmp     short loc_14000378E
0x140003773  mov     eax, 8000FFFFh
0x140003778  jmp     short loc_14000378E
0x14000377a  mov     eax, 8007007Ah
0x14000377f  mov     edx, 8000FFFFh
0x140003784  cmovnz  eax, edx
0x140003787  jmp     short loc_14000378E
0x140003789  mov     eax, 8007007Ah
0x14000378e  mov     rbx, [rsp+28h+arg_0]
0x140003793  mov     rbp, [rsp+28h+arg_8]
0x140003798  mov     rsi, [rsp+28h+arg_10]
0x14000379d  add     rsp, 20h
0x1400037a1  pop     rdi
0x1400037a2  retn
```
