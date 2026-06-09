# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x1800183f4`
- end: `0x180018560`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `364`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800181f0`
- `0x18003d0c0`
- `0x18003d190`
- `0x18007b134`

## callees

- `0x1800183f4`
- `0x18001a540`
- `0x18001cdf7`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018455`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018455`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018526`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018526`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001849b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800184f9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001849b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800184f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800184b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800184b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018510`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, DWORD a4, void **a5)
{
  HKEY v5; // rcx
  int v8; // esi
  LSTATUS v9; // eax
  int v10; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  v5 = HKEY_LOCAL_MACHINE;
  hkey = HKEY_LOCAL_MACHINE;
  if ( a2 && *a2 )
  {
    v8 = 1;
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, &hkey);
    v5 = hkey;
    v10 = v9;
  }
  else
  {
    v10 = 0;
    v8 = 0;
  }
  if ( v10 )
    goto LABEL_18;
  pcbData = 256;
  ValueW = RegGetValueW(v5, 0, a3, a4, 0, Src, &pcbData);
  v10 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v10 )
      {
        if ( RegGetValueW(hkey, 0, a3, a4, 0, pvData, &pcbData) )
        {
          v10 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          v10 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v10 = 14;
    }
  }
  if ( v8 )
    RegCloseKey(hkey);
  if ( v10 )
  {
LABEL_18:
    *a5 = 0;
    if ( v10 > 0 )
      return (unsigned __int16)v10 | 0x80070000;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800183f4  push    rbp
0x1800183f6  push    rbx
0x1800183f7  push    rsi
0x1800183f8  push    rdi
0x1800183f9  push    r12
0x1800183fb  push    r14
0x1800183fd  push    r15
0x1800183ff  lea     rbp, [rsp-60h]
0x180018404  sub     rsp, 160h
0x18001840b  mov     rax, cs:__security_cookie
0x180018412  xor     rax, rsp
0x180018415  mov     [rbp+90h+var_40], rax
0x180018419  mov     rdi, [rbp+90h+arg_20]
0x180018420  xor     r12d, r12d
0x180018423  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001842a  mov     r15d, r9d
0x18001842d  mov     [rsp+190h+hkey], rcx
0x180018432  mov     r14, r8
0x180018435  test    rdx, rdx
0x180018438  jz      short loc_180018464
0x18001843a  cmp     [rdx], r12w
0x18001843e  jz      short loc_180018464
0x180018440  lea     rax, [rsp+190h+hkey]
0x180018445  xor     r8d, r8d; ulOptions
0x180018448  lea     esi, [r12+1]
0x18001844d  mov     [rsp+190h+phkResult], rax; phkResult
0x180018452  mov     r9d, esi; samDesired
0x180018455  call    cs:__imp_RegOpenKeyExW
0x18001845b  mov     rcx, [rsp+190h+hkey]
0x180018460  mov     ebx, eax
0x180018462  jmp     short loc_18001846A
0x180018464  mov     ebx, r12d
0x180018467  mov     esi, r12d
0x18001846a  test    ebx, ebx
0x18001846c  jnz     loc_180018530
0x180018472  lea     rax, [rsp+190h+var_150]
0x180018477  mov     [rsp+190h+var_150], 100h
0x18001847f  mov     [rsp+190h+pcbData], rax; pcbData
0x180018484  mov     r9d, r15d; dwFlags
0x180018487  lea     rax, [rsp+190h+Src]
0x18001848c  mov     r8, r14; lpValue
0x18001848f  mov     [rsp+190h+pvData], rax; pvData
0x180018494  xor     edx, edx; lpSubKey
0x180018496  mov     [rsp+190h+phkResult], r12; pdwType
0x18001849b  call    cs:__imp_RegGetValueW
0x1800184a1  mov     ebx, eax
0x1800184a3  test    eax, eax
0x1800184a5  jz      short loc_1800184AE
0x1800184a7  cmp     eax, 0EAh
0x1800184ac  jnz     short loc_18001851D
0x1800184ae  mov     ecx, [rsp+190h+var_150]; cb
0x1800184b2  call    cs:__imp_CoTaskMemAlloc
0x1800184b8  mov     [rdi], rax
0x1800184bb  test    rax, rax
0x1800184be  jz      short loc_180018518
0x1800184c0  test    ebx, ebx
0x1800184c2  jnz     short loc_1800184D8
0x1800184c4  mov     r8d, [rsp+190h+var_150]; Size
0x1800184c9  lea     rdx, [rsp+190h+Src]; Src
0x1800184ce  mov     rcx, rax; void *
0x1800184d1  call    memcpy_0
0x1800184d6  jmp     short loc_18001851D
0x1800184d8  lea     rcx, [rsp+190h+var_150]
0x1800184dd  mov     r9d, r15d; dwFlags
0x1800184e0  mov     [rsp+190h+pcbData], rcx; pcbData
0x1800184e5  mov     r8, r14; lpValue
0x1800184e8  mov     rcx, [rsp+190h+hkey]; hkey
0x1800184ed  xor     edx, edx; lpSubKey
0x1800184ef  mov     [rsp+190h+pvData], rax; pvData
0x1800184f4  mov     [rsp+190h+phkResult], r12; pdwType
0x1800184f9  call    cs:__imp_RegGetValueW
0x1800184ff  test    eax, eax
0x180018501  jnz     short loc_180018508
0x180018503  mov     ebx, r12d
0x180018506  jmp     short loc_18001851D
0x180018508  mov     rcx, [rdi]; pv
0x18001850b  mov     ebx, 3EBh
0x180018510  call    cs:__imp_CoTaskMemFree
0x180018516  jmp     short loc_18001851D
0x180018518  mov     ebx, 0Eh
0x18001851d  test    esi, esi
0x18001851f  jz      short loc_18001852C
0x180018521  mov     rcx, [rsp+190h+hkey]; hKey
0x180018526  call    cs:__imp_RegCloseKey
0x18001852c  test    ebx, ebx
0x18001852e  jz      short loc_180018540
0x180018530  mov     [rdi], r12
0x180018533  test    ebx, ebx
0x180018535  jle     short loc_180018540
0x180018537  movzx   ebx, bx
0x18001853a  or      ebx, 80070000h
0x180018540  mov     eax, ebx
0x180018542  mov     rcx, [rbp+90h+var_40]
0x180018546  xor     rcx, rsp; StackCookie
0x180018549  call    __security_check_cookie
0x18001854e  add     rsp, 160h
0x180018555  pop     r15
0x180018557  pop     r14
0x180018559  pop     r12
0x18001855b  pop     rdi
0x18001855c  pop     rsi
0x18001855d  pop     rbx
0x18001855e  pop     rbp
0x18001855f  retn
```
