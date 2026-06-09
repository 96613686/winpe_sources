# PackDataToCredUI(unsigned __int64,ushort const *,ulong *,void * *,ulong *,HWND__ * *,ushort * *,ushort * *)

- ea: `0x180080df0`
- end: `0x180081038`
- name: `?PackDataToCredUI@@YAJ_KPEBGPEAKPEAPEAX2PEAPEAUHWND__@@PEAPEAG5@Z`
- size: `584`
- prototype: `__int64 __fastcall(unsigned __int64, const unsigned __int16 *, unsigned int *, void **, unsigned int *, HWND *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007db80`

## callees

- `0x180080df0`
- `0x1800812e4`
- `0x180081564`
- `0x180081654`
- `0x1800816e4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080fc5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080fd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080fed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081019`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080fc5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080fd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080fed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080fae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080fae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080ee3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080ee3`

## pseudocode

```c
__int64 __fastcall PackDataToCredUI(
        NCRYPT_HANDLE a1,
        const unsigned __int16 *a2,
        unsigned int *a3,
        void **a4,
        unsigned int *a5,
        HWND *a6,
        unsigned __int16 **a7,
        unsigned __int16 **a8)
{
  unsigned __int16 **v8; // rax
  unsigned __int16 *v9; // r14
  unsigned __int16 *v10; // rdi
  HLOCAL v11; // rsi
  int KeyProperties; // ebx
  int v13; // r8d
  int v14; // r9d
  LPVOID v15; // rax
  int v16; // r8d
  int v17; // r9d
  void *v18; // r12
  int v19; // eax
  unsigned int *v20; // rcx
  unsigned int cb; // [rsp+58h] [rbp-49h] BYREF
  int cb_4; // [rsp+5Ch] [rbp-45h] BYREF
  __int64 v24; // [rsp+60h] [rbp-41h] BYREF
  HLOCAL v25; // [rsp+68h] [rbp-39h]
  __int64 v26; // [rsp+70h] [rbp-31h] BYREF
  unsigned __int16 *v27; // [rsp+78h] [rbp-29h] BYREF
  HLOCAL v28; // [rsp+80h] [rbp-21h]
  unsigned __int16 *v29; // [rsp+88h] [rbp-19h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-11h] BYREF
  __int64 v31[8]; // [rsp+98h] [rbp-9h] BYREF
  __int64 v32; // [rsp+E8h] [rbp+47h] BYREF
  const unsigned __int16 *v33; // [rsp+F0h] [rbp+4Fh]
  unsigned int *v34; // [rsp+F8h] [rbp+57h]
  void **v35; // [rsp+100h] [rbp+5Fh]

  v35 = a4;
  v34 = a3;
  v33 = a2;
  v8 = a7;
  *a4 = 0;
  v9 = 0;
  LODWORD(v32) = 0;
  v10 = 0;
  LODWORD(v24) = 0;
  v11 = 0;
  *v8 = 0;
  v29 = 0;
  cb_4 = 0;
  v25 = 0;
  *a8 = 0;
  v28 = 0;
  v31[0] = 0;
  LODWORD(v26) = 0;
  v27 = 0;
  hMem = 0;
  cb = 0;
  if ( !a1 )
    return (unsigned int)-2146893786;
  KeyProperties = RetrieveKeyProperties(a1, (__int64)v31, (__int64)&v24, (__int64)&v32, (__int64)&cb_4, (__int64)&v26);
  if ( KeyProperties >= 0 )
  {
    KeyProperties = PackCredUIData(v24, (_DWORD)v25, v13, v14, cb_4, v32, (__int64)&cb, 0);
    if ( KeyProperties >= 0 )
    {
      v15 = CoTaskMemAlloc(cb);
      v18 = v15;
      if ( !v15 )
      {
        KeyProperties = -2146893810;
        goto LABEL_20;
      }
      KeyProperties = PackCredUIData(v24, (_DWORD)v25, v16, v17, cb_4, v32, (__int64)&cb, (__int64)v15);
      if ( KeyProperties >= 0 )
      {
        v19 = LoadTitleAndDescriptionFormatStrings((unsigned int)v32, v33, &v27, &hMem);
        v11 = hMem;
        KeyProperties = v19;
        if ( v19 >= 0 )
        {
          KeyProperties = ConstructMessageContentBuffer(hMem, v25, v28, &v29);
          if ( KeyProperties >= 0 )
          {
            *v34 = v26;
            v20 = a5;
            *v35 = v18;
            *v20 = cb;
            *a6 = (HWND)v31[0];
            *a7 = v29;
            *a8 = v27;
LABEL_14:
            if ( v10 )
              LocalFree(v10);
            if ( v9 )
              LocalFree(v9);
            if ( v11 )
              LocalFree(v11);
            goto LABEL_20;
          }
          v9 = v29;
        }
        v10 = v27;
      }
      CoTaskMemFree(v18);
      goto LABEL_14;
    }
  }
LABEL_20:
  if ( v25 )
    LocalFree(v25);
  if ( v28 )
    LocalFree(v28);
  return (unsigned int)KeyProperties;
}

```

## disassembly

```asm
0x180080df0  mov     rax, rsp
0x180080df3  mov     [rax+20h], r9
0x180080df7  mov     [rax+18h], r8
0x180080dfb  mov     [rax+10h], rdx
0x180080dff  push    rbp
0x180080e00  push    rbx
0x180080e01  push    rsi
0x180080e02  push    rdi
0x180080e03  push    r12
0x180080e05  push    r14
0x180080e07  lea     rbp, [rax-3Fh]
0x180080e0b  sub     rsp, 0A8h
0x180080e12  mov     rax, [rbp+37h+arg_30]
0x180080e16  xor     r12d, r12d
0x180080e19  mov     [r9], r12
0x180080e1c  mov     r14d, r12d
0x180080e1f  mov     dword ptr [rbp+37h+arg_0], r12d
0x180080e23  mov     edi, r12d
0x180080e26  mov     dword ptr [rbp+37h+var_78], r12d
0x180080e2a  mov     esi, r12d
0x180080e2d  mov     [rax], r12
0x180080e30  mov     rax, [rbp+37h+arg_38]
0x180080e34  mov     [rbp+37h+var_50], r12
0x180080e38  mov     dword ptr [rbp+37h+cb+4], r12d
0x180080e3c  mov     [rbp+37h+var_70], r12
0x180080e40  mov     [rax], r12
0x180080e43  mov     [rbp+37h+var_58], r12
0x180080e47  mov     [rbp+37h+var_40], r12
0x180080e4b  mov     dword ptr [rbp+37h+var_68], r12d
0x180080e4f  mov     [rbp+37h+var_60], r12
0x180080e53  mov     [rbp+37h+hMem], r12
0x180080e57  mov     dword ptr [rbp+37h+cb], r12d
0x180080e5b  test    rcx, rcx
0x180080e5e  jnz     short loc_180080E6A
0x180080e60  mov     ebx, 80090026h
0x180080e65  jmp     loc_180081025
0x180080e6a  lea     rax, [rbp+37h+var_68]
0x180080e6e  mov     [rsp+40h], rax; __int64
0x180080e73  lea     r9, [rbp+37h+var_58]
0x180080e77  lea     rax, [rbp+37h+cb+4]
0x180080e7b  mov     [rsp+0D0h+var_98], rax; __int64
0x180080e80  lea     r8, [rbp+37h+var_70]
0x180080e84  lea     rax, [rbp+37h+arg_0]
0x180080e88  mov     [rsp+0D0h+var_A0], rax; __int64
0x180080e8d  lea     rax, [rbp+37h+var_78]
0x180080e91  mov     [rsp+0D0h+var_A8], rax; __int64
0x180080e96  lea     rax, [rbp+37h+var_40]
0x180080e9a  mov     [rsp+0D0h+var_B0], rax; __int64
0x180080e9f  call    _RetrieveKeyProperties
0x180080ea4  mov     ebx, eax
0x180080ea6  test    eax, eax
0x180080ea8  js      loc_180080FF9
0x180080eae  mov     rdx, [rbp+37h+var_70]
0x180080eb2  lea     rax, [rbp+37h+cb]
0x180080eb6  mov     ecx, dword ptr [rbp+37h+var_78]
0x180080eb9  mov     [rsp+0D0h+var_98], r12
0x180080ebe  mov     [rsp+0D0h+var_A0], rax
0x180080ec3  mov     eax, dword ptr [rbp+37h+arg_0]
0x180080ec6  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180080eca  mov     eax, dword ptr [rbp+37h+cb+4]
0x180080ecd  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180080ed1  call    _PackCredUIData
0x180080ed6  mov     ebx, eax
0x180080ed8  test    eax, eax
0x180080eda  js      loc_180080FF9
0x180080ee0  mov     ecx, dword ptr [rbp+37h+cb]; cb
0x180080ee3  call    cs:__imp_CoTaskMemAlloc
0x180080eea  nop     dword ptr [rax+rax+00h]
0x180080eef  mov     r12, rax
0x180080ef2  test    rax, rax
0x180080ef5  jnz     short loc_180080F01
0x180080ef7  mov     ebx, 8009000Eh
0x180080efc  jmp     loc_180080FF9
0x180080f01  mov     rdx, [rbp+37h+var_70]
0x180080f05  lea     rax, [rbp+37h+cb]
0x180080f09  mov     ecx, dword ptr [rbp+37h+var_78]
0x180080f0c  mov     [rsp+0D0h+var_98], r12
0x180080f11  mov     [rsp+0D0h+var_A0], rax
0x180080f16  mov     eax, dword ptr [rbp+37h+arg_0]
0x180080f19  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180080f1d  mov     eax, dword ptr [rbp+37h+cb+4]
0x180080f20  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180080f24  call    _PackCredUIData
0x180080f29  mov     ebx, eax
0x180080f2b  test    eax, eax
0x180080f2d  js      short loc_180080FAB
0x180080f2f  mov     rdx, [rbp+37h+arg_8]
0x180080f33  lea     r9, [rbp+37h+hMem]
0x180080f37  mov     ecx, dword ptr [rbp+37h+arg_0]
0x180080f3a  lea     r8, [rbp+37h+var_60]
0x180080f3e  call    _LoadTitleAndDescriptionFormatStrings
0x180080f43  mov     rsi, [rbp+37h+hMem]
0x180080f47  mov     ebx, eax
0x180080f49  test    eax, eax
0x180080f4b  js      short loc_180080FA7
0x180080f4d  mov     r8, [rbp+37h+var_58]
0x180080f51  lea     r9, [rbp+37h+var_50]
0x180080f55  mov     rdx, [rbp+37h+var_70]
0x180080f59  mov     rcx, rsi
0x180080f5c  call    _ConstructMessageContentBuffer
0x180080f61  mov     ebx, eax
0x180080f63  test    eax, eax
0x180080f65  js      short loc_180080FA3
0x180080f67  mov     rcx, [rbp+37h+arg_10]
0x180080f6b  mov     eax, dword ptr [rbp+37h+var_68]
0x180080f6e  mov     [rcx], eax
0x180080f70  mov     rax, [rbp+37h+arg_18]
0x180080f74  mov     rcx, [rbp+37h+arg_20]
0x180080f78  mov     [rax], r12
0x180080f7b  mov     eax, dword ptr [rbp+37h+cb]
0x180080f7e  mov     [rcx], eax
0x180080f80  mov     rcx, [rbp+37h+arg_28]
0x180080f84  mov     rax, [rbp+37h+var_40]
0x180080f88  mov     [rcx], rax
0x180080f8b  mov     rcx, [rbp+37h+arg_30]
0x180080f8f  mov     rax, [rbp+37h+var_50]
0x180080f93  mov     [rcx], rax
0x180080f96  mov     rcx, [rbp+37h+arg_38]
0x180080f9a  mov     rax, [rbp+37h+var_60]
0x180080f9e  mov     [rcx], rax
0x180080fa1  jmp     short loc_180080FBA
0x180080fa3  mov     r14, [rbp+37h+var_50]
0x180080fa7  mov     rdi, [rbp+37h+var_60]
0x180080fab  mov     rcx, r12; pv
0x180080fae  call    cs:__imp_CoTaskMemFree
0x180080fb5  nop     dword ptr [rax+rax+00h]
0x180080fba  xor     r12d, r12d
0x180080fbd  test    rdi, rdi
0x180080fc0  jz      short loc_180080FD1
0x180080fc2  mov     rcx, rdi; hMem
0x180080fc5  call    cs:__imp_LocalFree
0x180080fcc  nop     dword ptr [rax+rax+00h]
0x180080fd1  test    r14, r14
0x180080fd4  jz      short loc_180080FE5
0x180080fd6  mov     rcx, r14; hMem
0x180080fd9  call    cs:__imp_LocalFree
0x180080fe0  nop     dword ptr [rax+rax+00h]
0x180080fe5  test    rsi, rsi
0x180080fe8  jz      short loc_180080FF9
0x180080fea  mov     rcx, rsi; hMem
0x180080fed  call    cs:__imp_LocalFree
0x180080ff4  nop     dword ptr [rax+rax+00h]
0x180080ff9  cmp     [rbp+37h+var_70], r12
0x180080ffd  jz      short loc_18008100F
0x180080fff  mov     rcx, [rbp+37h+var_70]; hMem
0x180081003  call    cs:__imp_LocalFree
0x18008100a  nop     dword ptr [rax+rax+00h]
0x18008100f  cmp     [rbp+37h+var_58], r12
0x180081013  jz      short loc_180081025
0x180081015  mov     rcx, [rbp+37h+var_58]; hMem
0x180081019  call    cs:__imp_LocalFree
0x180081020  nop     dword ptr [rax+rax+00h]
0x180081025  mov     eax, ebx
0x180081027  add     rsp, 0A8h
0x18008102e  pop     r14
0x180081030  pop     r12
0x180081032  pop     rdi
0x180081033  pop     rsi
0x180081034  pop     rbx
0x180081035  pop     rbp
0x180081036  retn
```
