# CSearchRegistryRedirectHelper::Initialize(unsigned __int64)

- ea: `0x18002b8b8`
- end: `0x18002b93d`
- name: `?Initialize@CSearchRegistryRedirectHelper@@QEAAJ_K@Z`
- size: `133`
- prototype: `__int64 __fastcall(CSearchRegistryRedirectHelper *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b7e0`

## callees

- `0x18000835c`
- `0x18002b8b8`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18002b8f7`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002b8f7`
- `ntdll!RtlNtStatusToDosError` at `0x18002b8ff`
- `ntdll!RtlNtStatusToDosError` at `0x18002b8ff`

## string_xrefs

- `0x18002b91d`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

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
  PersistedStateLocation = RtlGetPersistedStateLocation(off_1800588E0[69 * a2], 0, off_1800588E0[69 * a2 + 1], 0);
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
0x18002b8b8  push    rbx
0x18002b8ba  sub     rsp, 40h
0x18002b8be  mov     [rcx], rdx
0x18002b8c1  lea     r10, off_1800588E0; "WSearch"
0x18002b8c8  imul    rax, rdx, 228h
0x18002b8cf  add     rcx, 8
0x18002b8d3  mov     [rsp+48h+var_18], 0
0x18002b8dc  mov     [rsp+48h+var_20], 208h
0x18002b8e4  xor     r9d, r9d
0x18002b8e7  mov     qword ptr [rsp+48h+var_28], rcx; int
0x18002b8ec  xor     edx, edx
0x18002b8ee  mov     r8, [rax+r10+8]
0x18002b8f3  mov     rcx, [rax+r10]
0x18002b8f7  call    cs:__imp_RtlGetPersistedStateLocation
0x18002b8fd  mov     ecx, eax; Status
0x18002b8ff  call    cs:__imp_RtlNtStatusToDosError
0x18002b905  mov     ebx, eax
0x18002b907  test    eax, eax
0x18002b909  jle     short loc_18002B914
0x18002b90b  movzx   ebx, ax
0x18002b90e  or      ebx, 80070000h
0x18002b914  test    ebx, ebx
0x18002b916  jns     short loc_18002B935
0x18002b918  mov     rcx, [rsp+48h]; this
0x18002b91d  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\search\\com"...
0x18002b924  mov     r9d, ebx; char *
0x18002b927  mov     edx, 36h ; '6'; void *
0x18002b92c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b931  mov     eax, ebx
0x18002b933  jmp     short loc_18002B937
0x18002b935  xor     eax, eax
0x18002b937  add     rsp, 40h
0x18002b93b  pop     rbx
0x18002b93c  retn
```
