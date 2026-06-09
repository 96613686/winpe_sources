# sub_14000ECCC

- ea: `0x14000eccc`
- end: `0x14000ef04`
- name: `sub_14000ECCC`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400080b0`

## callees

- `0x140006f60`
- `0x14000795c`
- `0x14000eccc`
- `0x14000efa8`
- `0x1400c1a70`
- `0x1400ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ed6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ed6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ed55`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ed55`

## string_xrefs

- `0x14000ed4e`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall sub_14000ECCC(__int64 *a1)
{
  unsigned int v1; // ebx
  unsigned int v2; // esi
  int v4; // r15d
  HMODULE ModuleHandleW; // rax
  int v6; // edi
  unsigned int v7; // r9d
  __int64 v8; // r8
  int v9; // r10d
  unsigned __int64 v10; // rsi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  unsigned int v14; // [rsp+40h] [rbp-C0h]
  _DWORD v15[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v1 = 0;
  v2 = 0;
  if ( (unsigned __int64)(a1[1] - *a1) >= 0xC )
  {
    v4 = 0;
    do
    {
      memset(v15, 0, sizeof(v15));
      if ( NtQueryWnfStateData )
        goto LABEL_8;
      ModuleHandleW = lpSource;
      if ( !lpSource )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        lpSource = ModuleHandleW;
      }
      NtQueryWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
      if ( NtQueryWnfStateData )
      {
LABEL_8:
        v1 = sub_1400CA010(&qword_1400D08B8);
        v6 = v1;
        if ( !v1 )
        {
          v7 = 0;
          v14 = 0;
          v8 = *a1;
          v9 = 0;
          v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
          while ( v8 != v10 )
          {
            v11 = &v15[3 * v9];
            if ( v15 == v11 )
            {
LABEL_15:
              if ( (unsigned __int64)v7 + 12 <= 0x1000 )
              {
                v7 += 12;
                *(_QWORD *)v11 = *(_QWORD *)v8;
                ++v9;
                v11[2] = *(_DWORD *)(v8 + 8);
                v14 = v7;
              }
            }
            else
            {
              v12 = v15;
              while ( *v12 != *(_DWORD *)v8 || *((_WORD *)v12 + 2) != *(_WORD *)(v8 + 4) )
              {
                v12 += 3;
                if ( v12 == v11 )
                  goto LABEL_15;
              }
              v12[2] += *(_DWORD *)(v8 + 8);
              v7 = v14;
            }
            v8 += 12;
          }
          v2 = sub_14000EFA8((unsigned int)&qword_1400D08B8, (unsigned int)v15, v7, v7, (unsigned int)v15, 0, 1);
        }
      }
      else
      {
        v6 = -1073741511;
        v1 = -1073741511;
      }
      if ( v2 != -1073741823 )
        break;
      if ( ++v4 >= 100 )
        break;
    }
    while ( !v6 );
  }
  if ( !v1 )
    return v2;
  return v1;
}

```

## disassembly

```asm
0x14000eccc  push    rbp
0x14000ecce  push    rbx
0x14000eccf  push    rsi
0x14000ecd0  push    rdi
0x14000ecd1  push    r14
0x14000ecd3  push    r15
0x14000ecd5  lea     rbp, [rsp-0F68h]
0x14000ecdd  mov     eax, 1068h
0x14000ece2  call    __alloca_probe
0x14000ece7  sub     rsp, rax
0x14000ecea  mov     rax, cs:__security_cookie
0x14000ecf1  xor     rax, rsp
0x14000ecf4  mov     [rbp+0F90h+var_40], rax
0x14000ecfb  mov     rax, [rcx+8]
0x14000ecff  xor     ebx, ebx
0x14000ed01  sub     rax, [rcx]
0x14000ed04  xor     esi, esi
0x14000ed06  mov     r14, rcx
0x14000ed09  cmp     rax, 0Ch
0x14000ed0d  jb      loc_14000EED0
0x14000ed13  xor     r15d, r15d
0x14000ed16  xor     edx, edx; Val
0x14000ed18  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000ed1d  mov     r8d, 1000h; Size
0x14000ed23  call    memset
0x14000ed28  cmp     cs:NtQueryWnfStateData, 0
0x14000ed30  mov     [rsp+1090h+var_1050], 1000h
0x14000ed38  mov     [rsp+1090h+var_104C], 0
0x14000ed40  jnz     short loc_14000ED8A
0x14000ed42  mov     rax, cs:lpSource
0x14000ed49  test    rax, rax
0x14000ed4c  jnz     short loc_14000ED62
0x14000ed4e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000ed55  call    cs:GetModuleHandleW
0x14000ed5b  mov     cs:lpSource, rax
0x14000ed62  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000ed69  mov     rcx, rax; hModule
0x14000ed6c  call    cs:GetProcAddress
0x14000ed72  mov     cs:NtQueryWnfStateData, rax
0x14000ed79  test    rax, rax
0x14000ed7c  jnz     short loc_14000ED8A
0x14000ed7e  mov     edi, 0C0000139h
0x14000ed83  mov     ebx, edi
0x14000ed85  jmp     loc_14000EEB7
0x14000ed8a  lea     rax, [rsp+1090h+var_1050]
0x14000ed8f  xor     r8d, r8d
0x14000ed92  mov     [rsp+1090h+var_1068], rax
0x14000ed97  lea     r9, [rsp+1090h+var_104C]
0x14000ed9c  lea     rax, [rsp+1090h+var_1040]
0x14000eda1  xor     edx, edx
0x14000eda3  mov     [rsp+1090h+var_1070], rax
0x14000eda8  lea     rcx, qword_1400D08B8
0x14000edaf  mov     rax, cs:NtQueryWnfStateData
0x14000edb6  call    sub_1400CA010
0x14000edbb  mov     ebx, eax
0x14000edbd  mov     edi, eax
0x14000edbf  test    eax, eax
0x14000edc1  jnz     loc_14000EEB7
0x14000edc7  mov     r9d, [rsp+1090h+var_1050]
0x14000edcc  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000edd6  mov     rax, r11
0x14000edd9  mul     r9
0x14000eddc  shr     rdx, 3
0x14000ede0  lea     rcx, [rdx+rdx*2]
0x14000ede4  shl     rcx, 2
0x14000ede8  cmp     r9, rcx
0x14000edeb  jz      short loc_14000EDF5
0x14000eded  xor     r9d, r9d
0x14000edf0  mov     [rsp+1090h+var_1050], r9d
0x14000edf5  mov     r8, [r14]
0x14000edf8  mov     rax, r11
0x14000edfb  mov     ecx, r9d
0x14000edfe  mul     rcx
0x14000ee01  mov     rcx, [r14+8]
0x14000ee05  mov     rax, r11
0x14000ee08  mov     r10, rdx
0x14000ee0b  sub     rcx, r8
0x14000ee0e  mul     rcx
0x14000ee11  shr     r10, 3
0x14000ee15  shr     rdx, 3
0x14000ee19  lea     rax, [rdx+rdx*2]
0x14000ee1d  lea     rsi, [r8+rax*4]
0x14000ee21  jmp     short loc_14000EE8C
0x14000ee23  mov     eax, r10d
0x14000ee26  lea     rcx, [rax+rax*2]
0x14000ee2a  lea     rdx, [rdx+rcx*4]
0x14000ee2e  lea     rax, [rsp+1090h+var_1040]
0x14000ee33  cmp     rax, rdx
0x14000ee36  jz      short loc_14000EE5D
0x14000ee38  mov     r11d, [r8]
0x14000ee3b  lea     rcx, [rsp+1090h+var_1040]
0x14000ee40  cmp     [rcx], r11d
0x14000ee43  jnz     short loc_14000EE54
0x14000ee45  movzx   eax, word ptr [r8+4]
0x14000ee4a  cmp     [rcx+4], ax
0x14000ee4e  jz      loc_14000EEF6
0x14000ee54  add     rcx, 0Ch
0x14000ee58  cmp     rcx, rdx
0x14000ee5b  jnz     short loc_14000EE40
0x14000ee5d  mov     eax, r9d
0x14000ee60  add     rax, 0Ch
0x14000ee64  cmp     rax, 1000h
0x14000ee6a  ja      short loc_14000EE88
0x14000ee6c  movsd   xmm0, qword ptr [r8]
0x14000ee71  add     r9d, 0Ch
0x14000ee75  movsd   qword ptr [rdx], xmm0
0x14000ee79  inc     r10d
0x14000ee7c  mov     eax, [r8+8]
0x14000ee80  mov     [rdx+8], eax
0x14000ee83  mov     [rsp+1090h+var_1050], r9d
0x14000ee88  add     r8, 0Ch
0x14000ee8c  lea     rdx, [rsp+1090h+var_1040]
0x14000ee91  cmp     r8, rsi
0x14000ee94  jnz     short loc_14000EE23
0x14000ee96  mov     eax, [rsp+1090h+var_104C]
0x14000ee9a  lea     rcx, qword_1400D08B8
0x14000eea1  mov     [rsp+1090h+var_1060], 1
0x14000eea9  mov     r8d, r9d
0x14000eeac  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000eeb0  call    sub_14000EFA8
0x14000eeb5  mov     esi, eax
0x14000eeb7  cmp     esi, 0C0000001h
0x14000eebd  jnz     short loc_14000EED0
0x14000eebf  inc     r15d
0x14000eec2  cmp     r15d, 64h ; 'd'
0x14000eec6  jge     short loc_14000EED0
0x14000eec8  test    edi, edi
0x14000eeca  jz      loc_14000ED16
0x14000eed0  test    ebx, ebx
0x14000eed2  cmovz   ebx, esi
0x14000eed5  mov     eax, ebx
0x14000eed7  mov     rcx, [rbp+0F90h+var_40]
0x14000eede  xor     rcx, rsp; StackCookie
0x14000eee1  call    __security_check_cookie
0x14000eee6  add     rsp, 1068h
0x14000eeed  pop     r15
0x14000eeef  pop     r14
0x14000eef1  pop     rdi
0x14000eef2  pop     rsi
0x14000eef3  pop     rbx
0x14000eef4  pop     rbp
0x14000eef5  retn
0x14000eef6  mov     eax, [r8+8]
0x14000eefa  add     [rcx+8], eax
0x14000eefd  mov     r9d, [rsp+1090h+var_1050]
0x14000ef02  jmp     short loc_14000EE88
```
