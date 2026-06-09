# PROPERTY_MAPPING::Create(ushort const *,ushort const *,ulong,ulong,ulong,ulong,ulong,int,int,_MAP_HINT)

- ea: `0x180001b20`
- end: `0x180001f86`
- name: `?Create@PROPERTY_MAPPING@@QEAAJPEBG0KKKKKHHW4_MAP_HINT@@@Z`
- size: `1126`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800019a0`

## callees

- `0x180001b20`
- `0x180002990`
- `0x180019b50`
- `0x180019b64`
- `0x180019b78`
- `0x180019b8c`
- `0x180019ba0`
- `0x180019bb4`
- `0x180019bc8`
- `0x180019bdc`
- `0x180019bf0`
- `0x180019c04`
- `0x180019c18`
- `0x180019c2c`
- `0x180019c40`
- `0x180019c54`
- `0x180019c68`
- `0x180019c7c`
- `0x180019c90`
- `0x180019ca4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001c2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001c2e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180001c28`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180001c28`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001b37`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001b51`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001b37`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001b51`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001f6b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001f6b`

## string_xrefs

- `0x180001c21`: `%systemroot%\system32\inetsrv\ssinc.dll`

## pseudocode

```c
int __fastcall PROPERTY_MAPPING::Create(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11)
{
  int result; // eax
  int v15; // ebp
  CUSTOM_ERROR_CUSTOM_MAPPER *v16; // rbx
  DIRECTORY_BROWSING_CUSTOM_MAPPER *v17; // rax
  DEFAULT_LOAD_CUSTOM_MAPPER *v18; // rax
  CUSTOM_ERROR_CUSTOM_MAPPER *v19; // rax
  RESTRICTION_LIST_CUSTOM_MAPPER *v20; // rax
  HTTP_REDIRECT_CUSTOM_MAPPER *v21; // rax
  DEPENDENCIES_CUSTOM_MAPPER *v22; // rax
  CACHE_CONTROL_CUSTOM_MAPPER *v23; // rax
  HTTP_EXPIRES_CUSTOM_MAPPER *v24; // rax
  FOOTER_CUSTOM_MAPPER *v25; // rax
  MIMEMAP_CUSTOM_MAPPER *v26; // rax
  HTTP_TRACING_CUSTOM_MAPPER *v27; // rax
  AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER *v28; // rax
  PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER *v29; // rax
  LOGGING_PLUGIN_CUSTOM_MAPPER *v30; // rax
  IP_SECURITY_CUSTOM_MAPPER *v31; // rax
  LOGGING_ENABLED_CUSTOM_MAPPER *v32; // rax
  HEADER_CUSTOM_MAPPER *v33; // rax
  AUTHORIZATION_CUSTOM_MAPPER *v34; // rax

  result = STRU::Copy((STRU *)(a1 + 32), a2);
  if ( result >= 0 )
  {
    result = STRU::Copy((STRU *)(a1 + 88), a3);
    v15 = result;
    if ( result >= 0 )
    {
      *(_DWORD *)(a1 + 148) = a5;
      *(_DWORD *)(a1 + 152) = a6;
      *(_DWORD *)(a1 + 156) = a7;
      *(_DWORD *)(a1 + 160) = a8;
      *(_DWORD *)(a1 + 168) = a10;
      *(_DWORD *)(a1 + 164) = a9;
      *(_DWORD *)(a1 + 144) = a4;
      *(_DWORD *)(a1 + 172) = a11;
      if ( a4 == 2021 || a4 == 1023 )
      {
        v16 = (CUSTOM_ERROR_CUSTOM_MAPPER *)operator new(8u);
        if ( v16 )
        {
          *(_QWORD *)v16 = &SITE_BINDINGS_CUSTOM_MAPPER::`vftable';
          goto LABEL_68;
        }
      }
      else if ( a4 == 6000 || (unsigned int)(a4 - 6030) <= 1 )
      {
        v34 = (AUTHORIZATION_CUSTOM_MAPPER *)operator new(8u);
        if ( v34 )
        {
          v16 = AUTHORIZATION_CUSTOM_MAPPER::AUTHORIZATION_CUSTOM_MAPPER(v34);
          goto LABEL_68;
        }
      }
      else
      {
        switch ( a4 )
        {
          case 6014:
            v16 = (CUSTOM_ERROR_CUSTOM_MAPPER *)operator new(0x810u);
            if ( v16 )
            {
              *(_QWORD *)v16 = &SCRIPT_MAP_CUSTOM_MAPPER::`vftable';
              ExpandEnvironmentStringsW(L"%systemroot%\\system32\\inetsrv\\ssinc.dll", (LPWSTR)v16 + 4, 0x400u);
              *((_DWORD *)v16 + 514) = GetTickCount();
LABEL_68:
              *(_QWORD *)(a1 + 176) = v16;
              goto LABEL_69;
            }
            break;
          case 6005:
            v17 = (DIRECTORY_BROWSING_CUSTOM_MAPPER *)operator new(8u);
            if ( v17 )
            {
              v16 = DIRECTORY_BROWSING_CUSTOM_MAPPER::DIRECTORY_BROWSING_CUSTOM_MAPPER(v17);
              goto LABEL_68;
            }
            break;
          case 6006:
            v18 = (DEFAULT_LOAD_CUSTOM_MAPPER *)operator new(8u);
            if ( v18 )
            {
              v16 = DEFAULT_LOAD_CUSTOM_MAPPER::DEFAULT_LOAD_CUSTOM_MAPPER(v18);
              goto LABEL_68;
            }
            break;
          case 6008:
            v19 = (CUSTOM_ERROR_CUSTOM_MAPPER *)operator new(8u);
            if ( v19 )
            {
              v16 = CUSTOM_ERROR_CUSTOM_MAPPER::CUSTOM_ERROR_CUSTOM_MAPPER(v19);
              goto LABEL_68;
            }
            break;
          case 2168:
            v20 = (RESTRICTION_LIST_CUSTOM_MAPPER *)operator new(8u);
            if ( v20 )
            {
              v16 = RESTRICTION_LIST_CUSTOM_MAPPER::RESTRICTION_LIST_CUSTOM_MAPPER(v20);
              goto LABEL_68;
            }
            break;
          case 6011:
            v21 = (HTTP_REDIRECT_CUSTOM_MAPPER *)operator new(8u);
            if ( v21 )
            {
              v16 = HTTP_REDIRECT_CUSTOM_MAPPER::HTTP_REDIRECT_CUSTOM_MAPPER(v21);
              goto LABEL_68;
            }
            break;
          case 6004:
          case 6044:
            v33 = (HEADER_CUSTOM_MAPPER *)operator new(8u);
            if ( v33 )
            {
              v16 = HEADER_CUSTOM_MAPPER::HEADER_CUSTOM_MAPPER(v33);
              goto LABEL_68;
            }
            break;
          case 2167:
            v22 = (DEPENDENCIES_CUSTOM_MAPPER *)operator new(8u);
            if ( v22 )
            {
              v16 = DEPENDENCIES_CUSTOM_MAPPER::DEPENDENCIES_CUSTOM_MAPPER(v22);
              goto LABEL_68;
            }
            break;
          case 6041:
            v23 = (CACHE_CONTROL_CUSTOM_MAPPER *)operator new(8u);
            if ( v23 )
            {
              v16 = CACHE_CONTROL_CUSTOM_MAPPER::CACHE_CONTROL_CUSTOM_MAPPER(v23);
              goto LABEL_68;
            }
            break;
          case 6002:
            v24 = (HTTP_EXPIRES_CUSTOM_MAPPER *)operator new(8u);
            if ( v24 )
            {
              v16 = HTTP_EXPIRES_CUSTOM_MAPPER::HTTP_EXPIRES_CUSTOM_MAPPER(v24);
              goto LABEL_68;
            }
            break;
          case 6009:
            v25 = (FOOTER_CUSTOM_MAPPER *)operator new(8u);
            if ( v25 )
            {
              v16 = FOOTER_CUSTOM_MAPPER::FOOTER_CUSTOM_MAPPER(v25);
              goto LABEL_68;
            }
            break;
          case 6015:
            v26 = (MIMEMAP_CUSTOM_MAPPER *)operator new(8u);
            if ( v26 )
            {
              v16 = MIMEMAP_CUSTOM_MAPPER::MIMEMAP_CUSTOM_MAPPER(v26);
              goto LABEL_68;
            }
            break;
          case 2118:
            v27 = (HTTP_TRACING_CUSTOM_MAPPER *)operator new(8u);
            if ( v27 )
            {
              v16 = HTTP_TRACING_CUSTOM_MAPPER::HTTP_TRACING_CUSTOM_MAPPER(v27);
              goto LABEL_68;
            }
            break;
          case 6032:
            v28 = (AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER *)operator new(8u);
            if ( v28 )
            {
              v16 = AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER::AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER(v28);
              goto LABEL_68;
            }
            break;
          case 9020:
            v29 = (PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER *)operator new(8u);
            if ( v29 )
            {
              v16 = PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER::PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER(v29);
              goto LABEL_68;
            }
            break;
          case 2119:
          case 4016:
            v32 = (LOGGING_ENABLED_CUSTOM_MAPPER *)operator new(8u);
            if ( v32 )
            {
              v16 = LOGGING_ENABLED_CUSTOM_MAPPER::LOGGING_ENABLED_CUSTOM_MAPPER(v32);
              goto LABEL_68;
            }
            break;
          case 4011:
            v30 = (LOGGING_PLUGIN_CUSTOM_MAPPER *)operator new(8u);
            if ( v30 )
            {
              v16 = LOGGING_PLUGIN_CUSTOM_MAPPER::LOGGING_PLUGIN_CUSTOM_MAPPER(v30);
              goto LABEL_68;
            }
            break;
          case 6019:
            v31 = (IP_SECURITY_CUSTOM_MAPPER *)operator new(8u);
            if ( v31 )
            {
              v16 = IP_SECURITY_CUSTOM_MAPPER::IP_SECURITY_CUSTOM_MAPPER(v31);
              goto LABEL_68;
            }
            break;
          default:
LABEL_69:
            *(_DWORD *)(a1 + 16) = a4;
            *(_QWORD *)(a1 + 24) = STRU::QueryStr((STRU *)(a1 + 32));
            return v15;
        }
      }
      v16 = 0;
      goto LABEL_68;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001b20  push    rbx
0x180001b22  push    rsi
0x180001b23  push    rdi
0x180001b24  push    r14
0x180001b26  sub     rsp, 28h
0x180001b2a  mov     rdi, rcx
0x180001b2d  mov     esi, r9d
0x180001b30  add     rcx, 20h ; ' '
0x180001b34  mov     rbx, r8
0x180001b37  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001b3d  test    eax, eax
0x180001b3f  js      loc_180001F7C
0x180001b45  lea     rcx, [rdi+58h]
0x180001b49  mov     [rsp+48h+arg_0], rbp
0x180001b4e  mov     rdx, rbx
0x180001b51  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001b57  mov     ebp, eax
0x180001b59  test    eax, eax
0x180001b5b  js      loc_180001F77
0x180001b61  mov     ecx, [rsp+48h+arg_20]
0x180001b65  mov     eax, [rsp+48h+arg_48]
0x180001b6c  mov     [rdi+94h], ecx
0x180001b72  mov     ecx, [rsp+48h+arg_28]
0x180001b76  mov     [rdi+98h], ecx
0x180001b7c  mov     ecx, [rsp+48h+arg_30]
0x180001b83  mov     [rdi+9Ch], ecx
0x180001b89  mov     ecx, [rsp+48h+arg_38]
0x180001b90  mov     [rdi+0A0h], ecx
0x180001b96  mov     ecx, [rsp+48h+arg_40]
0x180001b9d  mov     [rdi+0A8h], eax
0x180001ba3  mov     eax, [rsp+48h+arg_50]
0x180001baa  mov     [rdi+0A4h], ecx
0x180001bb0  mov     [rdi+90h], esi
0x180001bb6  mov     [rdi+0ACh], eax
0x180001bbc  cmp     esi, 7E5h
0x180001bc2  jz      loc_180001F3D
0x180001bc8  cmp     esi, 3FFh
0x180001bce  jz      loc_180001F3D
0x180001bd4  cmp     esi, 1770h
0x180001bda  jz      loc_180001F21
0x180001be0  lea     eax, [rsi-178Eh]
0x180001be6  cmp     eax, 1
0x180001be9  jbe     loc_180001F21
0x180001bef  cmp     esi, 177Eh
0x180001bf5  jnz     short loc_180001C3F
0x180001bf7  mov     ecx, 810h; Size
0x180001bfc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001c01  mov     rbx, rax
0x180001c04  test    rax, rax
0x180001c07  jz      loc_180001F5B
0x180001c0d  lea     rax, ??_7SCRIPT_MAP_CUSTOM_MAPPER@@6B@; const SCRIPT_MAP_CUSTOM_MAPPER::`vftable'
0x180001c14  mov     r8d, 400h; nSize
0x180001c1a  lea     rdx, [rbx+8]; lpDst
0x180001c1e  mov     [rbx], rax
0x180001c21  lea     rcx, Src; "%systemroot%\\system32\\inetsrv\\ssinc."...
0x180001c28  call    cs:__imp_ExpandEnvironmentStringsW
0x180001c2e  call    cs:__imp_GetTickCount
0x180001c34  mov     [rbx+808h], eax
0x180001c3a  jmp     loc_180001F5D
0x180001c3f  cmp     esi, 1775h
0x180001c45  jnz     short loc_180001C6A
0x180001c47  mov     ecx, 8; Size
0x180001c4c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001c51  test    rax, rax
0x180001c54  jz      loc_180001F5B
0x180001c5a  mov     rcx, rax; this
0x180001c5d  call    ??0DIRECTORY_BROWSING_CUSTOM_MAPPER@@QEAA@XZ; DIRECTORY_BROWSING_CUSTOM_MAPPER::DIRECTORY_BROWSING_CUSTOM_MAPPER(void)
0x180001c62  mov     rbx, rax
0x180001c65  jmp     loc_180001F5D
0x180001c6a  cmp     esi, 1776h
0x180001c70  jnz     short loc_180001C95
0x180001c72  mov     ecx, 8; Size
0x180001c77  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001c7c  test    rax, rax
0x180001c7f  jz      loc_180001F5B
0x180001c85  mov     rcx, rax; this
0x180001c88  call    ??0DEFAULT_LOAD_CUSTOM_MAPPER@@QEAA@XZ; DEFAULT_LOAD_CUSTOM_MAPPER::DEFAULT_LOAD_CUSTOM_MAPPER(void)
0x180001c8d  mov     rbx, rax
0x180001c90  jmp     loc_180001F5D
0x180001c95  cmp     esi, 1778h
0x180001c9b  jnz     short loc_180001CC0
0x180001c9d  mov     ecx, 8; Size
0x180001ca2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001ca7  test    rax, rax
0x180001caa  jz      loc_180001F5B
0x180001cb0  mov     rcx, rax; this
0x180001cb3  call    ??0CUSTOM_ERROR_CUSTOM_MAPPER@@QEAA@XZ; CUSTOM_ERROR_CUSTOM_MAPPER::CUSTOM_ERROR_CUSTOM_MAPPER(void)
0x180001cb8  mov     rbx, rax
0x180001cbb  jmp     loc_180001F5D
0x180001cc0  cmp     esi, 878h
0x180001cc6  jnz     short loc_180001CEB
0x180001cc8  mov     ecx, 8; Size
0x180001ccd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001cd2  test    rax, rax
0x180001cd5  jz      loc_180001F5B
0x180001cdb  mov     rcx, rax; this
0x180001cde  call    ??0RESTRICTION_LIST_CUSTOM_MAPPER@@QEAA@XZ; RESTRICTION_LIST_CUSTOM_MAPPER::RESTRICTION_LIST_CUSTOM_MAPPER(void)
0x180001ce3  mov     rbx, rax
0x180001ce6  jmp     loc_180001F5D
0x180001ceb  cmp     esi, 177Bh
0x180001cf1  jnz     short loc_180001D16
0x180001cf3  mov     ecx, 8; Size
0x180001cf8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001cfd  test    rax, rax
0x180001d00  jz      loc_180001F5B
0x180001d06  mov     rcx, rax; this
0x180001d09  call    ??0HTTP_REDIRECT_CUSTOM_MAPPER@@QEAA@XZ; HTTP_REDIRECT_CUSTOM_MAPPER::HTTP_REDIRECT_CUSTOM_MAPPER(void)
0x180001d0e  mov     rbx, rax
0x180001d11  jmp     loc_180001F5D
0x180001d16  cmp     esi, 1774h
0x180001d1c  jz      loc_180001F05
0x180001d22  cmp     esi, 179Ch
0x180001d28  jz      loc_180001F05
0x180001d2e  cmp     esi, 877h
0x180001d34  jnz     short loc_180001D59
0x180001d36  mov     ecx, 8; Size
0x180001d3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001d40  test    rax, rax
0x180001d43  jz      loc_180001F5B
0x180001d49  mov     rcx, rax; this
0x180001d4c  call    ??0DEPENDENCIES_CUSTOM_MAPPER@@QEAA@XZ; DEPENDENCIES_CUSTOM_MAPPER::DEPENDENCIES_CUSTOM_MAPPER(void)
0x180001d51  mov     rbx, rax
0x180001d54  jmp     loc_180001F5D
0x180001d59  cmp     esi, 1799h
0x180001d5f  jnz     short loc_180001D84
0x180001d61  mov     ecx, 8; Size
0x180001d66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001d6b  test    rax, rax
0x180001d6e  jz      loc_180001F5B
0x180001d74  mov     rcx, rax; this
0x180001d77  call    ??0CACHE_CONTROL_CUSTOM_MAPPER@@QEAA@XZ; CACHE_CONTROL_CUSTOM_MAPPER::CACHE_CONTROL_CUSTOM_MAPPER(void)
0x180001d7c  mov     rbx, rax
0x180001d7f  jmp     loc_180001F5D
0x180001d84  cmp     esi, 1772h
0x180001d8a  jnz     short loc_180001DAF
0x180001d8c  mov     ecx, 8; Size
0x180001d91  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001d96  test    rax, rax
0x180001d99  jz      loc_180001F5B
0x180001d9f  mov     rcx, rax; this
0x180001da2  call    ??0HTTP_EXPIRES_CUSTOM_MAPPER@@QEAA@XZ; HTTP_EXPIRES_CUSTOM_MAPPER::HTTP_EXPIRES_CUSTOM_MAPPER(void)
0x180001da7  mov     rbx, rax
0x180001daa  jmp     loc_180001F5D
0x180001daf  cmp     esi, 1779h
0x180001db5  jnz     short loc_180001DDA
0x180001db7  mov     ecx, 8; Size
0x180001dbc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001dc1  test    rax, rax
0x180001dc4  jz      loc_180001F5B
0x180001dca  mov     rcx, rax; this
0x180001dcd  call    ??0FOOTER_CUSTOM_MAPPER@@QEAA@XZ; FOOTER_CUSTOM_MAPPER::FOOTER_CUSTOM_MAPPER(void)
0x180001dd2  mov     rbx, rax
0x180001dd5  jmp     loc_180001F5D
0x180001dda  cmp     esi, 177Fh
0x180001de0  jnz     short loc_180001E05
0x180001de2  mov     ecx, 8; Size
0x180001de7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001dec  test    rax, rax
0x180001def  jz      loc_180001F5B
0x180001df5  mov     rcx, rax; this
0x180001df8  call    ??0MIMEMAP_CUSTOM_MAPPER@@QEAA@XZ; MIMEMAP_CUSTOM_MAPPER::MIMEMAP_CUSTOM_MAPPER(void)
0x180001dfd  mov     rbx, rax
0x180001e00  jmp     loc_180001F5D
0x180001e05  cmp     esi, 846h
0x180001e0b  jnz     short loc_180001E30
0x180001e0d  mov     ecx, 8; Size
0x180001e12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001e17  test    rax, rax
0x180001e1a  jz      loc_180001F5B
0x180001e20  mov     rcx, rax; this
0x180001e23  call    ??0HTTP_TRACING_CUSTOM_MAPPER@@QEAA@XZ; HTTP_TRACING_CUSTOM_MAPPER::HTTP_TRACING_CUSTOM_MAPPER(void)
0x180001e28  mov     rbx, rax
0x180001e2b  jmp     loc_180001F5D
0x180001e30  cmp     esi, 1790h
0x180001e36  jnz     short loc_180001E5B
0x180001e38  mov     ecx, 8; Size
0x180001e3d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001e42  test    rax, rax
0x180001e45  jz      loc_180001F5B
0x180001e4b  mov     rcx, rax; this
0x180001e4e  call    ??0AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER@@QEAA@XZ; AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER::AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER(void)
0x180001e53  mov     rbx, rax
0x180001e56  jmp     loc_180001F5D
0x180001e5b  cmp     esi, 233Ch
0x180001e61  jnz     short loc_180001E86
0x180001e63  mov     ecx, 8; Size
0x180001e68  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001e6d  test    rax, rax
0x180001e70  jz      loc_180001F5B
0x180001e76  mov     rcx, rax; this
0x180001e79  call    ??0PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER@@QEAA@XZ; PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER::PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER(void)
0x180001e7e  mov     rbx, rax
0x180001e81  jmp     loc_180001F5D
0x180001e86  cmp     esi, 847h
0x180001e8c  jz      short loc_180001EE9
0x180001e8e  cmp     esi, 0FB0h
0x180001e94  jz      short loc_180001EE9
0x180001e96  cmp     esi, 0FABh
0x180001e9c  jnz     short loc_180001EC1
0x180001e9e  mov     ecx, 8; Size
0x180001ea3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001ea8  test    rax, rax
0x180001eab  jz      loc_180001F5B
0x180001eb1  mov     rcx, rax; this
0x180001eb4  call    ??0LOGGING_PLUGIN_CUSTOM_MAPPER@@QEAA@XZ; LOGGING_PLUGIN_CUSTOM_MAPPER::LOGGING_PLUGIN_CUSTOM_MAPPER(void)
0x180001eb9  mov     rbx, rax
0x180001ebc  jmp     loc_180001F5D
0x180001ec1  cmp     esi, 1783h
0x180001ec7  jnz     loc_180001F64
0x180001ecd  mov     ecx, 8; Size
0x180001ed2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001ed7  test    rax, rax
0x180001eda  jz      short loc_180001F5B
0x180001edc  mov     rcx, rax; this
0x180001edf  call    ??0IP_SECURITY_CUSTOM_MAPPER@@QEAA@XZ; IP_SECURITY_CUSTOM_MAPPER::IP_SECURITY_CUSTOM_MAPPER(void)
0x180001ee4  mov     rbx, rax
0x180001ee7  jmp     short loc_180001F5D
0x180001ee9  mov     ecx, 8; Size
0x180001eee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001ef3  test    rax, rax
0x180001ef6  jz      short loc_180001F5B
0x180001ef8  mov     rcx, rax; this
0x180001efb  call    ??0LOGGING_ENABLED_CUSTOM_MAPPER@@QEAA@XZ; LOGGING_ENABLED_CUSTOM_MAPPER::LOGGING_ENABLED_CUSTOM_MAPPER(void)
0x180001f00  mov     rbx, rax
0x180001f03  jmp     short loc_180001F5D
0x180001f05  mov     ecx, 8; Size
0x180001f0a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001f0f  test    rax, rax
0x180001f12  jz      short loc_180001F5B
0x180001f14  mov     rcx, rax; this
0x180001f17  call    ??0HEADER_CUSTOM_MAPPER@@QEAA@XZ; HEADER_CUSTOM_MAPPER::HEADER_CUSTOM_MAPPER(void)
0x180001f1c  mov     rbx, rax
0x180001f1f  jmp     short loc_180001F5D
0x180001f21  mov     ecx, 8; Size
0x180001f26  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001f2b  test    rax, rax
0x180001f2e  jz      short loc_180001F5B
0x180001f30  mov     rcx, rax; this
0x180001f33  call    ??0AUTHORIZATION_CUSTOM_MAPPER@@QEAA@XZ; AUTHORIZATION_CUSTOM_MAPPER::AUTHORIZATION_CUSTOM_MAPPER(void)
0x180001f38  mov     rbx, rax
0x180001f3b  jmp     short loc_180001F5D
0x180001f3d  mov     ecx, 8; Size
0x180001f42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001f47  mov     rbx, rax
0x180001f4a  test    rax, rax
0x180001f4d  jz      short loc_180001F5B
0x180001f4f  lea     rax, ??_7SITE_BINDINGS_CUSTOM_MAPPER@@6B@; const SITE_BINDINGS_CUSTOM_MAPPER::`vftable'
0x180001f56  mov     [rbx], rax
0x180001f59  jmp     short loc_180001F5D
0x180001f5b  xor     ebx, ebx
0x180001f5d  mov     [rdi+0B0h], rbx
0x180001f64  lea     rcx, [rdi+20h]
0x180001f68  mov     [rdi+10h], esi
0x180001f6b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180001f71  mov     [rdi+18h], rax
0x180001f75  mov     eax, ebp
0x180001f77  mov     rbp, [rsp+48h+arg_0]
0x180001f7c  add     rsp, 28h
0x180001f80  pop     r14
0x180001f82  pop     rdi
0x180001f83  pop     rsi
0x180001f84  pop     rbx
0x180001f85  retn
```
