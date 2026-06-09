# RegisterWnfListener(SERVICE_STATUS_HANDLE__ *,_WNF_USER_SUBSCRIPTION * *,_WNF_STATE_NAME,long (*)(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong),ushort const *)

- ea: `0x1800018c0`
- end: `0x18000199d`
- name: `?RegisterWnfListener@@YAJPEAUSERVICE_STATUS_HANDLE__@@PEAPEAU_WNF_USER_SUBSCRIPTION@@U_WNF_STATE_NAME@@P6AJ2KPEAU_WNF_TYPE_ID@@PEAXPEBXK@ZPEBG@Z`
- size: `221`
- prototype: `__int64 __fastcall(struct SERVICE_STATUS_HANDLE__ *, struct _WNF_USER_SUBSCRIPTION **, struct _WNF_STATE_NAME, int (*)(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int), LPCWSTR lpValue)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180005f00`

## callees

- `0x1800018c0`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180001974`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180001974`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000193d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000193d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001981`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001981`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x1800018ed`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x1800018ed`

## pseudocode

```c
__int64 __fastcall RegisterWnfListener(
        struct SERVICE_STATUS_HANDLE__ *a1,
        struct _WNF_USER_SUBSCRIPTION **a2,
        struct _WNF_STATE_NAME a3,
        int (*a4)(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int),
        LPCWSTR lpValue)
{
  __int64 result; // rax
  bool v9; // sf
  __int64 v10; // r8
  int v11; // ebx
  unsigned int pvData; // [rsp+40h] [rbp-38h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-34h] BYREF
  HKEY hkey[6]; // [rsp+48h] [rbp-30h] BYREF

  hkey[0] = 0;
  pvData = 0;
  result = GetServiceRegistryStateKey(a1, 1, 131097, hkey);
  v9 = (int)result < 0;
  if ( (int)result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v9 = (int)result < 0;
  }
  if ( !v9 )
  {
    pcbData = 4;
    if ( RegGetValueW(hkey[0], 0, lpValue, 0x18u, 0, &pvData, &pcbData) )
    {
      v10 = 0;
      pvData = 0;
    }
    else
    {
      v10 = pvData;
    }
    v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))RtlSubscribeWnfStateChangeNotification)(
            a2,
            a3,
            v10,
            a4,
            0,
            0,
            0,
            4);
    RegCloseKey(hkey[0]);
    result = 0;
    if ( v11 )
      return v11 | 0x10000000u;
  }
  return result;
}

```

## disassembly

```asm
0x1800018c0  push    rbx
0x1800018c2  push    rbp
0x1800018c3  push    rsi
0x1800018c4  push    rdi
0x1800018c5  sub     rsp, 58h
0x1800018c9  mov     rdi, r9
0x1800018cc  mov     rbx, r8
0x1800018cf  mov     rsi, rdx
0x1800018d2  lea     r9, [rsp+78h+hkey]
0x1800018d7  xor     ebp, ebp
0x1800018d9  mov     edx, 1
0x1800018de  mov     r8d, 20019h
0x1800018e4  mov     [rsp+78h+hkey], rbp
0x1800018e9  mov     [rsp+78h+var_38], ebp
0x1800018ed  call    cs:__imp_GetServiceRegistryStateKey
0x1800018f3  test    eax, eax
0x1800018f5  jle     short loc_180001901
0x1800018f7  movzx   eax, ax
0x1800018fa  or      eax, 80070000h
0x1800018ff  test    eax, eax
0x180001901  js      loc_180001994
0x180001907  mov     r8, [rsp+78h+lpValue]; lpValue
0x18000190f  lea     rax, [rsp+78h+var_34]
0x180001914  mov     rcx, [rsp+78h+hkey]; hkey
0x180001919  mov     r9d, 18h; dwFlags
0x18000191f  mov     [rsp+78h+pcbData], rax; pcbData
0x180001924  xor     edx, edx; lpSubKey
0x180001926  lea     rax, [rsp+78h+var_38]
0x18000192b  mov     [rsp+78h+var_34], 4
0x180001933  mov     [rsp+78h+pvData], rax; pvData
0x180001938  mov     [rsp+78h+pdwType], rbp; pdwType
0x18000193d  call    cs:__imp_RegGetValueW
0x180001943  test    eax, eax
0x180001945  jz      short loc_180001950
0x180001947  mov     r8d, ebp
0x18000194a  mov     [rsp+78h+var_38], ebp
0x18000194e  jmp     short loc_180001955
0x180001950  mov     r8d, [rsp+78h+var_38]
0x180001955  mov     [rsp+78h+var_40], 4
0x18000195d  mov     r9, rdi
0x180001960  mov     dword ptr [rsp+78h+pcbData], ebp
0x180001964  mov     rdx, rbx
0x180001967  mov     [rsp+78h+pvData], rbp
0x18000196c  mov     rcx, rsi
0x18000196f  mov     [rsp+78h+pdwType], rbp
0x180001974  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18000197a  mov     rcx, [rsp+78h+hkey]; hKey
0x18000197f  mov     ebx, eax
0x180001981  call    cs:__imp_RegCloseKey
0x180001987  mov     ecx, ebx
0x180001989  mov     eax, ebp
0x18000198b  bts     ecx, 1Ch
0x18000198f  test    ebx, ebx
0x180001991  cmovnz  eax, ecx
0x180001994  add     rsp, 58h
0x180001998  pop     rdi
0x180001999  pop     rsi
0x18000199a  pop     rbp
0x18000199b  pop     rbx
0x18000199c  retn
```
