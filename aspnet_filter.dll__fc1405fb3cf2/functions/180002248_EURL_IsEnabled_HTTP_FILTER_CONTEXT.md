# EURL::IsEnabled(_HTTP_FILTER_CONTEXT *)

- ea: `0x180002248`
- end: `0x18000229d`
- name: `?IsEnabled@EURL@@SAHPEAU_HTTP_FILTER_CONTEXT@@@Z`
- size: `85`
- prototype: `__int64 __fastcall(struct _HTTP_FILTER_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001ba0`

## callees

- `0x180002248`
- `0x1800022a0`

## pseudocode

```c
__int64 __fastcall EURL::IsEnabled(struct _HTTP_FILTER_CONTEXT *a1)
{
  unsigned int v1; // ebx

  v1 = 0;
  if ( EURL::sm_fIIS6 && EURL::sm_fNeedToCheckScriptMap )
  {
    if ( !(unsigned int)EURL::IsScriptMappedAndEnabled(a1) )
    {
      EURL::sm_pszEURLAppendage = 0;
      LODWORD(EURL::sm_cchEURLAppendage) = 0;
      EURL::sm_pszEURLAppendageW = 0;
      EURL::sm_cchEURLAppendageW = 0;
    }
    EURL::sm_fNeedToCheckScriptMap = 0;
  }
  LOBYTE(v1) = EURL::sm_pszEURLAppendage != 0;
  return v1;
}

```

## disassembly

```asm
0x180002248  push    rbx
0x18000224a  sub     rsp, 20h
0x18000224e  xor     ebx, ebx
0x180002250  cmp     cs:?sm_fIIS6@EURL@@0HA, ebx; int EURL::sm_fIIS6
0x180002256  jz      short loc_18000228B
0x180002258  mov     eax, cs:?sm_fNeedToCheckScriptMap@EURL@@0HC; int volatile EURL::sm_fNeedToCheckScriptMap
0x18000225e  test    eax, eax
0x180002260  jz      short loc_18000228B
0x180002262  call    ?IsScriptMappedAndEnabled@EURL@@CAHPEAU_HTTP_FILTER_CONTEXT@@@Z; EURL::IsScriptMappedAndEnabled(_HTTP_FILTER_CONTEXT *)
0x180002267  test    eax, eax
0x180002269  jnz     short loc_180002285
0x18000226b  mov     cs:?sm_pszEURLAppendage@EURL@@0PEADEA, rbx; char * EURL::sm_pszEURLAppendage
0x180002272  mov     cs:?sm_cchEURLAppendage@EURL@@0KA, ebx; ulong EURL::sm_cchEURLAppendage
0x180002278  mov     cs:?sm_pszEURLAppendageW@EURL@@0PEAGEA, rbx; ushort * EURL::sm_pszEURLAppendageW
0x18000227f  mov     cs:?sm_cchEURLAppendageW@EURL@@0KA, ebx; ulong EURL::sm_cchEURLAppendageW
0x180002285  mov     cs:?sm_fNeedToCheckScriptMap@EURL@@0HC, ebx; int volatile EURL::sm_fNeedToCheckScriptMap
0x18000228b  cmp     cs:?sm_pszEURLAppendage@EURL@@0PEADEA, rbx; char * EURL::sm_pszEURLAppendage
0x180002292  setnz   bl
0x180002295  mov     eax, ebx
0x180002297  add     rsp, 20h
0x18000229b  pop     rbx
0x18000229c  retn
```
