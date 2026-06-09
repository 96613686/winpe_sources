# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x1800177c8`
- end: `0x180017933`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `363`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, __int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012dc0`
- `0x18002f4f8`

## callees

- `0x180009f30`
- `0x1800177c8`
- `0x180036250`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800178f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800178f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001781f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001781f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017866`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800178c7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017866`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800178c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800178de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800178de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001787d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001787d`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  int v6; // esi
  LSTATUS v7; // eax
  int v8; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  hkey = a1;
  if ( a2 && *a2 )
  {
    v6 = 1;
    v7 = RegOpenKeyExW(a1, a2, 0, 1u, &hkey);
    a1 = hkey;
    v8 = v7;
  }
  else
  {
    v8 = 0;
    v6 = 0;
  }
  if ( v8 )
    goto LABEL_18;
  pcbData = 256;
  ValueW = RegGetValueW(a1, 0, a3, 2u, 0, Src, &pcbData);
  v8 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v8 )
      {
        if ( RegGetValueW(hkey, 0, a3, 2u, 0, pvData, &pcbData) )
        {
          v8 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          v8 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v8 = 14;
    }
  }
  if ( v6 )
    RegCloseKey(hkey);
  if ( v8 )
  {
LABEL_18:
    *a5 = 0;
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800177c8  mov     [rsp-8+arg_18], rbx
0x1800177cd  push    rbp
0x1800177ce  push    rsi
0x1800177cf  push    rdi
0x1800177d0  push    r14
0x1800177d2  push    r15
0x1800177d4  lea     rbp, [rsp-60h]
0x1800177d9  sub     rsp, 160h
0x1800177e0  mov     rax, cs:__security_cookie
0x1800177e7  xor     rax, rsp
0x1800177ea  mov     [rbp+80h+var_30], rax
0x1800177ee  mov     rdi, [rbp+80h+arg_20]
0x1800177f5  xor     r15d, r15d
0x1800177f8  mov     [rsp+180h+hkey], rcx
0x1800177fd  mov     r14, r8
0x180017800  test    rdx, rdx
0x180017803  jz      short loc_18001782E
0x180017805  cmp     [rdx], r15w
0x180017809  jz      short loc_18001782E
0x18001780b  lea     rax, [rsp+180h+hkey]
0x180017810  xor     r8d, r8d; ulOptions
0x180017813  lea     esi, [r15+1]
0x180017817  mov     [rsp+180h+phkResult], rax; phkResult
0x18001781c  mov     r9d, esi; samDesired
0x18001781f  call    cs:__imp_RegOpenKeyExW
0x180017825  mov     rcx, [rsp+180h+hkey]; hkey
0x18001782a  mov     ebx, eax
0x18001782c  jmp     short loc_180017834
0x18001782e  mov     ebx, r15d
0x180017831  mov     esi, r15d
0x180017834  test    ebx, ebx
0x180017836  jnz     loc_1800178FE
0x18001783c  lea     rax, [rsp+180h+var_140]
0x180017841  mov     [rsp+180h+var_140], 100h
0x180017849  mov     [rsp+180h+pcbData], rax; pcbData
0x18001784e  lea     r9d, [rbx+2]; dwFlags
0x180017852  lea     rax, [rsp+180h+Src]
0x180017857  mov     r8, r14; lpValue
0x18001785a  mov     [rsp+180h+pvData], rax; pvData
0x18001785f  xor     edx, edx; lpSubKey
0x180017861  mov     [rsp+180h+phkResult], r15; pdwType
0x180017866  call    cs:__imp_RegGetValueW
0x18001786c  mov     ebx, eax
0x18001786e  test    eax, eax
0x180017870  jz      short loc_180017879
0x180017872  cmp     eax, 0EAh
0x180017877  jnz     short loc_1800178EB
0x180017879  mov     ecx, [rsp+180h+var_140]; cb
0x18001787d  call    cs:__imp_CoTaskMemAlloc
0x180017883  mov     [rdi], rax
0x180017886  test    rax, rax
0x180017889  jz      short loc_1800178E6
0x18001788b  test    ebx, ebx
0x18001788d  jnz     short loc_1800178A3
0x18001788f  mov     r8d, [rsp+180h+var_140]; Size
0x180017894  lea     rdx, [rsp+180h+Src]; Src
0x180017899  mov     rcx, rax; void *
0x18001789c  call    memcpy_0
0x1800178a1  jmp     short loc_1800178EB
0x1800178a3  lea     rcx, [rsp+180h+var_140]
0x1800178a8  mov     r9d, 2; dwFlags
0x1800178ae  mov     [rsp+180h+pcbData], rcx; pcbData
0x1800178b3  mov     r8, r14; lpValue
0x1800178b6  mov     rcx, [rsp+180h+hkey]; hkey
0x1800178bb  xor     edx, edx; lpSubKey
0x1800178bd  mov     [rsp+180h+pvData], rax; pvData
0x1800178c2  mov     [rsp+180h+phkResult], r15; pdwType
0x1800178c7  call    cs:__imp_RegGetValueW
0x1800178cd  test    eax, eax
0x1800178cf  jnz     short loc_1800178D6
0x1800178d1  mov     ebx, r15d
0x1800178d4  jmp     short loc_1800178EB
0x1800178d6  mov     rcx, [rdi]; pv
0x1800178d9  mov     ebx, 3EBh
0x1800178de  call    cs:__imp_CoTaskMemFree
0x1800178e4  jmp     short loc_1800178EB
0x1800178e6  mov     ebx, 0Eh
0x1800178eb  test    esi, esi
0x1800178ed  jz      short loc_1800178FA
0x1800178ef  mov     rcx, [rsp+180h+hkey]; hKey
0x1800178f4  call    cs:__imp_RegCloseKey
0x1800178fa  test    ebx, ebx
0x1800178fc  jz      short loc_18001790E
0x1800178fe  mov     [rdi], r15
0x180017901  test    ebx, ebx
0x180017903  jle     short loc_18001790E
0x180017905  movzx   ebx, bx
0x180017908  or      ebx, 80070000h
0x18001790e  mov     eax, ebx
0x180017910  mov     rcx, [rbp+80h+var_30]
0x180017914  xor     rcx, rsp; StackCookie
0x180017917  call    __security_check_cookie
0x18001791c  mov     rbx, [rsp+180h+arg_18]
0x180017924  add     rsp, 160h
0x18001792b  pop     r15
0x18001792d  pop     r14
0x18001792f  pop     rdi
0x180017930  pop     rsi
0x180017931  pop     rbp
0x180017932  retn
```
