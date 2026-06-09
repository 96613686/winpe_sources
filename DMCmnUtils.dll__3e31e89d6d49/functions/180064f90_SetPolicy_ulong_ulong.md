# SetPolicy(ulong,ulong)

- ea: `0x180064f90`
- end: `0x1800651dc`
- name: `?SetPolicy@@YAHKK@Z`
- size: `588`
- prototype: `int(unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x18000186c`
- `0x180007270`
- `0x180007c7c`
- `0x180058420`
- `0x1800617f0`
- `0x180064f90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800650d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800650d0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180065122`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180065122`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800651a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800651a6`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18006509b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18006509b`

## pseudocode

```c
_BOOL8 __fastcall SetPolicy(unsigned int a1, unsigned int a2)
{
  int v4; // r9d
  __int64 v5; // rdx
  struct POLICYNODE near **v6; // r8
  int v7; // ecx
  signed int v8; // ebx
  char IsStateSeparationEnabled; // al
  WCHAR *v10; // rdx
  LSTATUS v11; // eax
  HKEY v12; // rcx
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v16; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v17; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 v18[8]; // [rsp+68h] [rbp-98h] BYREF
  int v19; // [rsp+78h] [rbp-88h]
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  v19 = 0;
  *(_OWORD *)v18 = 0;
  memset_0(SubKey, 0, 0x208u);
  v5 = 0;
  hKey = 0;
  v6 = &g_listAllNodes;
  while ( 1 )
  {
    v7 = 5 * v5;
    if ( a1 == *((_DWORD *)&g_listAllNodes + 5 * v5) )
      break;
    v5 = (unsigned int)(v5 + 1);
    if ( (unsigned int)v5 >= 0xE )
    {
      v8 = -2147023728;
      goto LABEL_20;
    }
  }
  v7 = 5 * v5;
  if ( *((_DWORD *)&g_listAllNodes + 5 * (int)v5 + 2) )
  {
    if ( (~*((_DWORD *)&g_listAllNodes + 5 * (int)v5 + 3) & a2) != 0 )
    {
LABEL_8:
      v8 = -2147024809;
      goto LABEL_20;
    }
  }
  else if ( a2 > *((_DWORD *)&g_listAllNodes + 5 * (int)v5 + 4) || a2 < *((_DWORD *)&g_listAllNodes + 5 * (int)v5 + 3) )
  {
    goto LABEL_8;
  }
  v8 = StringCchPrintfW(
         SubKey,
         0x104u,
         L"%s\\%s",
         c_pszMutableSubKey,
         &aDm[11 * *((unsigned int *)&g_listAllNodes + 5 * (int)v5 + 1)]);
  if ( v8 >= 0 )
  {
    v8 = StringCchPrintfW(v18, 0xAu, L"%08x", a1);
    if ( v8 >= 0 )
    {
      IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
      v10 = SubKey;
      if ( IsStateSeparationEnabled )
      {
        if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey) )
        {
          dwDisposition = 0;
          v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
          v8 = v11;
          if ( v11 )
          {
            if ( v11 > 0 )
              v8 = (unsigned __int16)v11 | 0x80070000;
            goto LABEL_20;
          }
        }
        v12 = hKey;
        v10 = 0;
      }
      else
      {
        v12 = HKEY_LOCAL_MACHINE;
      }
      v8 = OmaDmRegistrySetDWORD(v12, v10, v18, a2);
    }
  }
LABEL_20:
  if ( (unsigned int)dword_180102138 > 4 )
  {
    dwDisposition = v8;
    v16 = a2;
    v17 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)byte_1800EA953,
      (_DWORD)v6,
      v4,
      (__int64)&v17,
      (__int64)&v16,
      (__int64)&dwDisposition);
  }
  RegCloseKey(hKey);
  return v8 >= 0;
}

```

## disassembly

```asm
0x180064f90  mov     [rsp-8+arg_10], rbx
0x180064f95  push    rbp
0x180064f96  push    rsi
0x180064f97  push    rdi
0x180064f98  lea     rbp, [rsp-1A0h]
0x180064fa0  sub     rsp, 2A0h
0x180064fa7  mov     rax, cs:__security_cookie
0x180064fae  xor     rax, rsp
0x180064fb1  mov     [rbp+1B0h+var_20], rax
0x180064fb8  mov     edi, edx
0x180064fba  mov     esi, ecx
0x180064fbc  xorps   xmm0, xmm0
0x180064fbf  lea     rcx, [rbp+1B0h+SubKey]; void *
0x180064fc3  xor     eax, eax
0x180064fc5  xor     edx, edx; Val
0x180064fc7  mov     r8d, 208h; Size
0x180064fcd  mov     [rsp+2B0h+var_238], eax
0x180064fd1  movups  xmmword ptr [rsp+2B0h+var_248], xmm0
0x180064fd6  call    memset_0
0x180064fdb  xor     edx, edx
0x180064fdd  mov     [rsp+2B0h+hKey], 0
0x180064fe6  lea     r8, ?g_listAllNodes@@3PAUPOLICYNODE@@A; POLICYNODE near * g_listAllNodes
0x180064fed  lea     rcx, [rdx+rdx*4]
0x180064ff1  cmp     esi, [r8+rcx*4]
0x180064ff5  jz      short loc_180065008
0x180064ff7  inc     edx
0x180064ff9  cmp     edx, 0Eh
0x180064ffc  jb      short loc_180064FED
0x180064ffe  mov     ebx, 80070490h
0x180065003  jmp     loc_180065160
0x180065008  movsxd  rax, edx
0x18006500b  lea     rcx, [rax+rax*4]
0x18006500f  cmp     dword ptr [r8+rcx*4+8], 0
0x180065015  jnz     short loc_18006502F
0x180065017  cmp     edi, [r8+rcx*4+10h]
0x18006501c  ja      short loc_180065025
0x18006501e  cmp     edi, [r8+rcx*4+0Ch]
0x180065023  jnb     short loc_18006503A
0x180065025  mov     ebx, 80070057h
0x18006502a  jmp     loc_180065160
0x18006502f  mov     eax, [r8+rcx*4+0Ch]
0x180065034  not     eax
0x180065036  test    edi, eax
0x180065038  jnz     short loc_180065025
0x18006503a  mov     eax, [r8+rcx*4+4]
0x18006503f  mov     edx, 104h; unsigned __int64
0x180065044  mov     r9, cs:?c_pszMutableSubKey@@3PEBGEB; ushort const * const c_pszMutableSubKey
0x18006504b  lea     r8, aSS; "%s\\%s"
0x180065052  imul    rcx, rax, 16h
0x180065056  lea     rax, aDm; "DM"
0x18006505d  add     rcx, rax
0x180065060  mov     [rsp+2B0h+phkResult], rcx
0x180065065  lea     rcx, [rbp+1B0h+SubKey]; unsigned __int16 *
0x180065069  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006506e  mov     ebx, eax
0x180065070  test    eax, eax
0x180065072  js      loc_180065160
0x180065078  mov     r9d, esi
0x18006507b  lea     r8, a08x; "%08x"
0x180065082  mov     edx, 0Ah; unsigned __int64
0x180065087  lea     rcx, [rsp+2B0h+var_248]; unsigned __int16 *
0x18006508c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180065091  mov     ebx, eax
0x180065093  test    eax, eax
0x180065095  js      loc_180065160
0x18006509b  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800650a2  nop     dword ptr [rax+rax+00h]
0x1800650a7  lea     rdx, [rbp+1B0h+SubKey]; unsigned __int16 *
0x1800650ab  test    al, al
0x1800650ad  jz      loc_18006514A
0x1800650b3  lea     rax, [rsp+2B0h+hKey]
0x1800650b8  mov     rbx, 0FFFFFFFF80000002h
0x1800650bf  mov     rcx, rbx; hKey
0x1800650c2  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1800650c7  mov     r9d, 0F003Fh; samDesired
0x1800650cd  xor     r8d, r8d; ulOptions
0x1800650d0  call    cs:__imp_RegOpenKeyExW
0x1800650d7  nop     dword ptr [rax+rax+00h]
0x1800650dc  test    eax, eax
0x1800650de  jz      short loc_180065141
0x1800650e0  lea     rax, [rsp+2B0h+dwDisposition]
0x1800650e5  mov     [rsp+2B0h+dwDisposition], 0
0x1800650ed  mov     [rsp+2B0h+lpdwDisposition], rax; lpdwDisposition
0x1800650f2  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x1800650f6  lea     rax, [rsp+2B0h+hKey]
0x1800650fb  xor     r9d, r9d; lpClass
0x1800650fe  mov     [rsp+2B0h+var_278], rax; phkResult
0x180065103  xor     r8d, r8d; Reserved
0x180065106  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006510f  mov     rcx, rbx; hKey
0x180065112  mov     [rsp+2B0h+samDesired], 0F003Fh; samDesired
0x18006511a  mov     dword ptr [rsp+2B0h+phkResult], 0; dwOptions
0x180065122  call    cs:__imp_RegCreateKeyExW
0x180065129  nop     dword ptr [rax+rax+00h]
0x18006512e  mov     ebx, eax
0x180065130  test    eax, eax
0x180065132  jz      short loc_180065141
0x180065134  jle     short loc_180065160
0x180065136  movzx   ebx, ax
0x180065139  or      ebx, 80070000h
0x18006513f  jmp     short loc_180065160
0x180065141  mov     rcx, [rsp+2B0h+hKey]
0x180065146  xor     edx, edx
0x180065148  jmp     short loc_180065151
0x18006514a  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180065151  mov     r9d, edi; unsigned int
0x180065154  lea     r8, [rsp+2B0h+var_248]; unsigned __int16 *
0x180065159  call    ?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18006515e  mov     ebx, eax
0x180065160  mov     eax, cs:dword_180102138
0x180065166  cmp     eax, 4
0x180065169  jbe     short loc_1800651A1
0x18006516b  lea     rax, [rsp+2B0h+dwDisposition]
0x180065170  mov     [rsp+2B0h+dwDisposition], ebx
0x180065174  mov     [rsp+2B0h+lpSecurityAttributes], rax
0x180065179  lea     rdx, byte_1800EA953
0x180065180  lea     rax, [rsp+2B0h+var_250]
0x180065185  mov     [rsp+2B0h+var_250], edi
0x180065189  mov     qword ptr [rsp+2B0h+samDesired], rax
0x18006518e  lea     rax, [rsp+2B0h+var_24C]
0x180065193  mov     [rsp+2B0h+phkResult], rax
0x180065198  mov     [rsp+2B0h+var_24C], esi
0x18006519c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800651a1  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800651a6  call    cs:__imp_RegCloseKey
0x1800651ad  nop     dword ptr [rax+rax+00h]
0x1800651b2  not     ebx
0x1800651b4  shr     ebx, 1Fh
0x1800651b7  mov     eax, ebx
0x1800651b9  mov     rcx, [rbp+1B0h+var_20]
0x1800651c0  xor     rcx, rsp; StackCookie
0x1800651c3  call    __security_check_cookie
0x1800651c8  mov     rbx, [rsp+2B0h+arg_10]
0x1800651d0  add     rsp, 2A0h
0x1800651d7  pop     rdi
0x1800651d8  pop     rsi
0x1800651d9  pop     rbp
0x1800651da  retn
```
