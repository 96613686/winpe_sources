# RegUtils::GetVolatileRegistryLocation(MapsRegKeys,ushort *,ulong)

- ea: `0x18000d04c`
- end: `0x18000d0d0`
- name: `?GetVolatileRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z`
- size: `132`
- prototype: `int __fastcall(__int64, _WORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000cbb8`

## callees

- `0x18000d04c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000d0c5`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000d0c5`

## string_xrefs

- `0x18000d0bb`: `RegUtils::GetVolatileRegistryLocation`

## pseudocode

```c
int __fastcall RegUtils::GetVolatileRegistryLocation(__int64 a1, _WORD *a2)
{
  __int64 v2; // rax
  const wchar_t *v3; // rcx
  __int64 v4; // r8
  _WORD *v5; // rcx

  v2 = 2147483646;
  v3 = L"System\\Maps\\Storage\\Volatile";
  v4 = 260;
  do
  {
    if ( !v2 )
      break;
    if ( !*v3 )
      break;
    *a2++ = *v3++;
    --v2;
    --v4;
  }
  while ( v4 );
  v5 = a2 - 1;
  if ( v4 )
    v5 = a2;
  *v5 = 0;
  if ( v4 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(-2147024774, "RegUtils::GetVolatileRegistryLocation", 1082);
}

```

## disassembly

```asm
0x18000d04c  sub     rsp, 28h
0x18000d050  mov     eax, 7FFFFFFEh
0x18000d055  lea     rcx, aSystemMapsStor_0; "System\\Maps\\Storage\\Volatile"
0x18000d05c  mov     r8d, 104h
0x18000d062  xor     r10d, r10d
0x18000d065  test    rax, rax
0x18000d068  jz      short loc_18000D089
0x18000d06a  movzx   r9d, word ptr [rcx]
0x18000d06e  test    r9w, r9w
0x18000d072  jz      short loc_18000D089
0x18000d074  mov     [rdx], r9w
0x18000d078  add     rcx, 2
0x18000d07c  add     rdx, 2
0x18000d080  dec     rax
0x18000d083  sub     r8, 1
0x18000d087  jnz     short loc_18000D065
0x18000d089  mov     rax, r8
0x18000d08c  lea     rcx, [rdx-2]
0x18000d090  neg     rax
0x18000d093  sbb     r9d, r9d
0x18000d096  not     r9d
0x18000d099  and     r9d, 8007007Ah
0x18000d0a0  test    r8, r8
0x18000d0a3  cmovnz  rcx, rdx
0x18000d0a7  mov     [rcx], r10w
0x18000d0ab  jz      short loc_18000D0B5
0x18000d0ad  mov     eax, r10d
0x18000d0b0  add     rsp, 28h
0x18000d0b4  retn
0x18000d0b5  mov     r8d, 43Ah
0x18000d0bb  lea     rdx, aRegutilsGetvol; "RegUtils::GetVolatileRegistryLocation"
0x18000d0c2  mov     ecx, r9d
0x18000d0c5  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000d0cb  add     rsp, 28h
0x18000d0cf  retn
```
