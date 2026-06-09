# CSearchRegistryRedirectHelper::Initialize(unsigned __int64)

- ea: `0x14002aa38`
- end: `0x14002aabd`
- name: `?Initialize@CSearchRegistryRedirectHelper@@QEAAJ_K@Z`
- size: `133`
- prototype: `__int64 __fastcall(CSearchRegistryRedirectHelper *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14002a960`

## callees

- `0x140009f14`
- `0x14002aa38`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14002aa7f`
- `ntdll!RtlNtStatusToDosError` at `0x14002aa7f`
- `ntdll!RtlGetPersistedStateLocation` at `0x14002aa77`
- `ntdll!RtlGetPersistedStateLocation` at `0x14002aa77`

## string_xrefs

- `0x14002aa9d`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

## pseudocode

```c
__int64 __fastcall CSearchRegistryRedirectHelper::Initialize(CSearchRegistryRedirectHelper *this, __int64 a2)
{
  NTSTATUS PersistedStateLocation; // eax
  signed int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)this = a2;
  v6 = (_DWORD)this + 8;
  PersistedStateLocation = RtlGetPersistedStateLocation(off_14006A210[69 * a2], 0, off_14006A210[69 * a2 + 1], 0);
  v3 = RtlNtStatusToDosError(PersistedStateLocation);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( (v4 & 0x80000000) == 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x36,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
    (const char *)v4,
    v6);
  return v4;
}

```

## disassembly

```asm
0x14002aa38  push    rbx
0x14002aa3a  sub     rsp, 40h
0x14002aa3e  mov     [rcx], rdx
0x14002aa41  lea     r10, off_14006A210; "WSearch"
0x14002aa48  imul    rax, rdx, 228h
0x14002aa4f  add     rcx, 8
0x14002aa53  mov     [rsp+48h+var_18], 0
0x14002aa5c  mov     [rsp+48h+var_20], 208h
0x14002aa64  xor     r9d, r9d
0x14002aa67  mov     qword ptr [rsp+48h+var_28], rcx; int
0x14002aa6c  xor     edx, edx
0x14002aa6e  mov     r8, [rax+r10+8]
0x14002aa73  mov     rcx, [rax+r10]
0x14002aa77  call    cs:__imp_RtlGetPersistedStateLocation
0x14002aa7d  mov     ecx, eax; Status
0x14002aa7f  call    cs:__imp_RtlNtStatusToDosError
0x14002aa85  mov     ebx, eax
0x14002aa87  test    eax, eax
0x14002aa89  jle     short loc_14002AA94
0x14002aa8b  movzx   ebx, ax
0x14002aa8e  or      ebx, 80070000h
0x14002aa94  test    ebx, ebx
0x14002aa96  jns     short loc_14002AAB5
0x14002aa98  mov     rcx, [rsp+48h]; this
0x14002aa9d  lea     r8, aOnecoreuapBase_37; "onecoreuap\\base\\appmodel\\search\\com"...
0x14002aaa4  mov     r9d, ebx; char *
0x14002aaa7  mov     edx, 36h ; '6'; void *
0x14002aaac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002aab1  mov     eax, ebx
0x14002aab3  jmp     short loc_14002AAB7
0x14002aab5  xor     eax, eax
0x14002aab7  add     rsp, 40h
0x14002aabb  pop     rbx
0x14002aabc  retn
```
