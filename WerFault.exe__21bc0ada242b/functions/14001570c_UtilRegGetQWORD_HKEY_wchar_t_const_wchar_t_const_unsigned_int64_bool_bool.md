# UtilRegGetQWORD(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64,bool *,bool)

- ea: `0x14001570c`
- end: `0x1400157e6`
- name: `?UtilRegGetQWORD@@YA_KPEAUHKEY__@@PEB_W1_KPEA_N_N@Z`
- size: `218`
- prototype: `unsigned __int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, unsigned __int64@<r9>, bool *, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001241c`
- `0x140028550`

## callees

- `0x140005468`
- `0x14001570c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400157a6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400157a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400157d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400157d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001576c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001576c`

## pseudocode

```c
__int64 __fastcall UtilRegGetQWORD(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValue, __int64 a4, bool *a5, DWORD pcbData)
{
  bool *v6; // rdi
  HKEY *phkResult; // rax
  __int64 v11; // rbx
  HKEY hkey; // [rsp+60h] [rbp+8h] BYREF
  __int64 pvData; // [rsp+78h] [rbp+20h] BYREF

  v6 = a5;
  pvData = 0;
  pcbData = 8;
  hkey = 0;
  if ( a5 )
    *a5 = 0;
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  if ( RegOpenKeyExW(hKey, lpSubKey, 0, 0x101u, phkResult)
    || RegGetValueW(hkey, 0, lpValue, 0x40u, 0, &pvData, &pcbData) )
  {
    v11 = 0;
    pvData = 0;
    if ( v6 )
      *v6 = 1;
  }
  else
  {
    v11 = pvData;
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v11;
}

```

## disassembly

```asm
0x14001570c  mov     rax, rsp
0x14001570f  mov     [rax+10h], rbx
0x140015713  mov     [rax+20h], r9
0x140015717  push    rbp
0x140015718  push    rsi
0x140015719  push    rdi
0x14001571a  sub     rsp, 40h
0x14001571e  mov     rdi, [rsp+58h+arg_20]
0x140015726  mov     rbx, r8
0x140015729  mov     qword ptr [rax+20h], 0
0x140015731  mov     rsi, rdx
0x140015734  mov     dword ptr [rax+30h], 8
0x14001573b  mov     rbp, rcx
0x14001573e  mov     qword ptr [rax+8], 0
0x140015746  test    rdi, rdi
0x140015749  jz      short loc_14001574E
0x14001574b  mov     byte ptr [rdi], 0
0x14001574e  lea     rcx, [rsp+58h+hkey]
0x140015753  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140015758  mov     r9d, 101h; samDesired
0x14001575e  mov     [rsp+58h+phkResult], rax; phkResult
0x140015763  xor     r8d, r8d; ulOptions
0x140015766  mov     rdx, rsi; lpSubKey
0x140015769  mov     rcx, rbp; hKey
0x14001576c  call    cs:__imp_RegOpenKeyExW
0x140015772  test    eax, eax
0x140015774  jnz     short loc_1400157B7
0x140015776  mov     rcx, [rsp+58h+hkey]; hkey
0x14001577b  lea     rax, [rsp+58h+arg_28]
0x140015783  mov     [rsp+58h+pcbData], rax; pcbData
0x140015788  mov     r9d, 40h ; '@'; dwFlags
0x14001578e  lea     rax, [rsp+58h+arg_18]
0x140015793  mov     r8, rbx; lpValue
0x140015796  mov     [rsp+58h+pvData], rax; pvData
0x14001579b  xor     edx, edx; lpSubKey
0x14001579d  mov     [rsp+58h+phkResult], 0; pdwType
0x1400157a6  call    cs:__imp_RegGetValueW
0x1400157ac  test    eax, eax
0x1400157ae  jnz     short loc_1400157B7
0x1400157b0  mov     rbx, [rsp+58h+arg_18]
0x1400157b5  jmp     short loc_1400157C6
0x1400157b7  xor     ebx, ebx
0x1400157b9  mov     [rsp+58h+arg_18], rbx
0x1400157be  test    rdi, rdi
0x1400157c1  jz      short loc_1400157C6
0x1400157c3  mov     byte ptr [rdi], 1
0x1400157c6  mov     rcx, [rsp+58h+hkey]; hKey
0x1400157cb  test    rcx, rcx
0x1400157ce  jz      short loc_1400157D6
0x1400157d0  call    cs:__imp_RegCloseKey
0x1400157d6  mov     rax, rbx
0x1400157d9  mov     rbx, [rsp+58h+arg_8]
0x1400157de  add     rsp, 40h
0x1400157e2  pop     rdi
0x1400157e3  pop     rsi
0x1400157e4  pop     rbp
0x1400157e5  retn
```
