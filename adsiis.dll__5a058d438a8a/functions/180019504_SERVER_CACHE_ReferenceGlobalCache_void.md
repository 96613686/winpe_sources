# SERVER_CACHE::ReferenceGlobalCache(void)

- ea: `0x180019504`
- end: `0x180019589`
- name: `?ReferenceGlobalCache@SERVER_CACHE@@SAXXZ`
- size: `133`
- prototype: `void(void)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180001ad0`
- `0x18000d380`
- `0x18000fe60`
- `0x180014794`

## callees

- `0x1800010b0`
- `0x180019304`
- `0x180019334`
- `0x180019444`
- `0x180019504`

## string_xrefs

- `0x180019567`: `\n\n==========================================\nadsiis!sm_pServerCache=%p\n\n`

## pseudocode

```c
void __fastcall SERVER_CACHE::ReferenceGlobalCache(__int64 a1, struct WIN32_CRITSEC *a2)
{
  SERVER_CACHE *v2; // rax
  SERVER_CACHE *v3; // rdx
  char *v4; // rax
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  CLock::CLock((CLock *)&v5, a2);
  if ( v5 )
  {
    ++SERVER_CACHE::sm_cRefs;
    if ( !SERVER_CACHE::sm_pServerCache )
    {
      v2 = (SERVER_CACHE *)operator new(0x40u);
      v3 = v2;
      if ( v2 )
      {
        *((_QWORD *)v2 + 2) = 0;
        *((_QWORD *)v2 + 1) = 5;
        v4 = (char *)v2 + 24;
        *(_QWORD *)v3 = v4;
        *(_OWORD *)v4 = 0;
        *((_OWORD *)v4 + 1) = 0;
        *((_QWORD *)v4 + 4) = 0;
      }
      else
      {
        v3 = 0;
      }
      SERVER_CACHE::sm_pServerCache = v3;
      AdsiTrace(L"\n\n==========================================\nadsiis!sm_pServerCache=%p\n\n");
    }
  }
  CLock::~CLock((CLock *)&v5);
}

```

## disassembly

```asm
0x180019504  sub     rsp, 28h
0x180019508  lea     rcx, [rsp+28h+arg_0]; this
0x18001950d  call    ??0CLock@@QEAA@PEAVWIN32_CRITSEC@@@Z; CLock::CLock(WIN32_CRITSEC *)
0x180019512  cmp     [rsp+28h+arg_0], 0
0x180019518  jz      short loc_18001957A
0x18001951a  inc     cs:?sm_cRefs@SERVER_CACHE@@1JA; long SERVER_CACHE::sm_cRefs
0x180019520  cmp     cs:?sm_pServerCache@SERVER_CACHE@@1PEAV1@EA, 0; SERVER_CACHE * SERVER_CACHE::sm_pServerCache
0x180019528  jnz     short loc_18001957A
0x18001952a  mov     ecx, 40h ; '@'; Size
0x18001952f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019534  mov     rdx, rax
0x180019537  test    rax, rax
0x18001953a  jz      short loc_180019565
0x18001953c  mov     qword ptr [rax+10h], 0
0x180019544  xorps   xmm0, xmm0
0x180019547  mov     qword ptr [rax+8], 5
0x18001954f  add     rax, 18h
0x180019553  mov     [rdx], rax
0x180019556  xor     ecx, ecx
0x180019558  movups  xmmword ptr [rax], xmm0
0x18001955b  movups  xmmword ptr [rax+10h], xmm0
0x18001955f  mov     [rax+20h], rcx
0x180019563  jmp     short loc_180019567
0x180019565  xor     edx, edx
0x180019567  lea     rcx, aAdsiisSmPserve; "\n\n==================================="...
0x18001956e  mov     cs:?sm_pServerCache@SERVER_CACHE@@1PEAV1@EA, rdx; SERVER_CACHE * SERVER_CACHE::sm_pServerCache
0x180019575  call    ?AdsiTrace@@YAXPEBGZZ; AdsiTrace(ushort const *,...)
0x18001957a  lea     rcx, [rsp+28h+arg_0]; this
0x18001957f  call    ??1CLock@@QEAA@XZ; CLock::~CLock(void)
0x180019584  add     rsp, 28h
0x180019588  retn
```
