# BdeCfgIsWinREOnOSVolume(int *)

- ea: `0x180004b00`
- end: `0x180004c3b`
- name: `?BdeCfgIsWinREOnOSVolume@@YAJPEAH@Z`
- size: `315`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x1800040d0`
- `0x180004b00`
- `0x180007210`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180004be1`
- `msvcrt!_wcsicmp` at `0x180004be1`
- `ole32!CoTaskMemFree` at `0x180004bfb`
- `ole32!CoTaskMemFree` at `0x180004bfb`

## pseudocode

```c
__int64 __fastcall BdeCfgIsWinREOnOSVolume(int *a1)
{
  struct IVdsVolume *v2; // rdi
  unsigned int v3; // ebx
  signed int v4; // eax
  int BootVolume; // eax
  int v6; // eax
  struct IVdsVolume *v8; // [rsp+20h] [rbp-E0h] BYREF
  _OWORD v9[3]; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-A8h]
  wchar_t String2[264]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(String2, 0, 0x208u);
  v2 = 0;
  String1 = 0;
  v8 = 0;
  memset(v9, 0, sizeof(v9));
  if ( g_pService )
  {
    if ( a1 )
    {
      *a1 = 0;
      v4 = BdeCfgDetectWinREVolumeName(0x104u, String2);
      v3 = v4;
      if ( v4 >= 0 )
      {
        if ( v4 == 1 )
        {
          v3 = 0;
        }
        else
        {
          BootVolume = BdeCfgGetBootVolume(&v8);
          v2 = v8;
          v3 = BootVolume;
          if ( BootVolume >= 0 )
          {
            v6 = ((__int64 (__fastcall *)(struct IVdsVolume *, _OWORD *))v8->lpVtbl->GetProperties)(v8, v9);
            v3 = v6;
            if ( v6 >= 0 )
            {
              if ( v6 == 272149 && String1 )
                v3 = 0;
              if ( !_wcsicmp(String1, String2) )
                *a1 = 1;
            }
          }
        }
      }
    }
    else
    {
      v3 = -2147467261;
    }
  }
  else
  {
    v3 = -1063256042;
  }
  if ( String1 )
  {
    CoTaskMemFree(String1);
    String1 = 0;
  }
  if ( v2 )
    ((void (__fastcall *)(struct IVdsVolume *))v2->lpVtbl->Release)(v2);
  return v3;
}

```

## disassembly

```asm
0x180004b00  push    rbp
0x180004b02  push    rbx
0x180004b03  push    rsi
0x180004b04  push    rdi
0x180004b05  lea     rbp, [rsp-188h]
0x180004b0d  sub     rsp, 288h
0x180004b14  mov     rax, cs:__security_cookie
0x180004b1b  xor     rax, rsp
0x180004b1e  mov     [rbp+1A0h+var_30], rax
0x180004b25  mov     rsi, rcx
0x180004b28  xor     edx, edx; Val
0x180004b2a  lea     rcx, [rsp+2A0h+String2]; void *
0x180004b2f  mov     r8d, 208h; Size
0x180004b35  call    memset_0
0x180004b3a  xorps   xmm0, xmm0
0x180004b3d  xor     eax, eax
0x180004b3f  xor     edi, edi
0x180004b41  mov     [rsp+2A0h+String1], rax
0x180004b46  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, rax; IVdsService * g_pService
0x180004b4d  mov     [rsp+2A0h+var_280], rdi
0x180004b52  movups  [rsp+2A0h+var_278], xmm0
0x180004b57  movups  [rsp+2A0h+var_268], xmm0
0x180004b5c  movups  [rsp+2A0h+var_258], xmm0
0x180004b61  jnz     short loc_180004B6D
0x180004b63  mov     ebx, 0C0A00016h
0x180004b68  jmp     loc_180004BF1
0x180004b6d  test    rsi, rsi
0x180004b70  jnz     short loc_180004B79
0x180004b72  mov     ebx, 80004003h
0x180004b77  jmp     short loc_180004BF1
0x180004b79  lea     rdx, [rsp+2A0h+String2]; unsigned __int16 *
0x180004b7e  mov     [rsi], eax
0x180004b80  mov     ecx, 104h; unsigned __int64
0x180004b85  call    ?BdeCfgDetectWinREVolumeName@@YAJ_KPEAG@Z; BdeCfgDetectWinREVolumeName(unsigned __int64,ushort *)
0x180004b8a  mov     ebx, eax
0x180004b8c  test    eax, eax
0x180004b8e  js      short loc_180004BF1
0x180004b90  cmp     eax, 1
0x180004b93  jnz     short loc_180004B99
0x180004b95  xor     ebx, ebx
0x180004b97  jmp     short loc_180004BF1
0x180004b99  lea     rcx, [rsp+2A0h+var_280]; struct IVdsVolume **
0x180004b9e  call    ?BdeCfgGetBootVolume@@YAJPEAPEAUIVdsVolume@@@Z; BdeCfgGetBootVolume(IVdsVolume * *)
0x180004ba3  mov     rdi, [rsp+2A0h+var_280]
0x180004ba8  mov     ebx, eax
0x180004baa  test    eax, eax
0x180004bac  js      short loc_180004BF1
0x180004bae  mov     rax, [rdi]
0x180004bb1  lea     rdx, [rsp+2A0h+var_278]
0x180004bb6  mov     rcx, rdi
0x180004bb9  mov     rax, [rax+18h]
0x180004bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bc2  mov     ebx, eax
0x180004bc4  test    eax, eax
0x180004bc6  js      short loc_180004BF1
0x180004bc8  mov     rcx, [rsp+2A0h+String1]; String1
0x180004bcd  cmp     eax, 42715h
0x180004bd2  jnz     short loc_180004BDC
0x180004bd4  xor     eax, eax
0x180004bd6  test    rcx, rcx
0x180004bd9  cmovnz  ebx, eax
0x180004bdc  lea     rdx, [rsp+2A0h+String2]; String2
0x180004be1  call    cs:__imp__wcsicmp
0x180004be7  test    eax, eax
0x180004be9  jnz     short loc_180004BF1
0x180004beb  mov     dword ptr [rsi], 1
0x180004bf1  mov     rcx, [rsp+2A0h+String1]; pv
0x180004bf6  test    rcx, rcx
0x180004bf9  jz      short loc_180004C0A
0x180004bfb  call    cs:__imp_CoTaskMemFree
0x180004c01  mov     [rsp+2A0h+String1], 0
0x180004c0a  test    rdi, rdi
0x180004c0d  jz      short loc_180004C1E
0x180004c0f  mov     rax, [rdi]
0x180004c12  mov     rcx, rdi
0x180004c15  mov     rax, [rax+10h]
0x180004c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c1e  mov     eax, ebx
0x180004c20  mov     rcx, [rbp+1A0h+var_30]
0x180004c27  xor     rcx, rsp; StackCookie
0x180004c2a  call    __security_check_cookie
0x180004c2f  add     rsp, 288h
0x180004c36  pop     rdi
0x180004c37  pop     rsi
0x180004c38  pop     rbx
0x180004c39  pop     rbp
0x180004c3a  retn
```
