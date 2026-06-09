# ACUtil::GetAppContainerSidFromMoniker(ushort const *,void * *)

- ea: `0x180052da4`
- end: `0x180052df5`
- name: `?GetAppContainerSidFromMoniker@ACUtil@@SAJPEBGPEAPEAX@Z`
- size: `81`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003912c`
- `0x18008610c`

## callees

- `0x180052da4`

## import_xrefs

- `USERENV!CreateAppContainerProfile` at `0x180052dd2`
- `USERENV!CreateAppContainerProfile` at `0x180052dd2`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x180052de9`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x180052de9`

## pseudocode

```c
__int64 __fastcall ACUtil::GetAppContainerSidFromMoniker(const unsigned __int16 *a1, void **a2)
{
  __int64 result; // rax

  result = CreateAppContainerProfile(
             L"microsoft^windows^spellchecking^host",
             L"microsoft^windows^spellchecking^host",
             L"microsoft^windows^spellchecking^host",
             0,
             0,
             a2);
  if ( (_DWORD)result == -2147024713 )
    return DeriveAppContainerSidFromAppContainerName(L"microsoft^windows^spellchecking^host", a2);
  return result;
}

```

## disassembly

```asm
0x180052da4  push    rbx
0x180052da6  sub     rsp, 30h
0x180052daa  mov     [rsp+38h+var_10], rdx
0x180052daf  lea     r8, aMicrosoftWindo; "microsoft^windows^spellchecking^host"
0x180052db6  mov     rbx, rdx
0x180052db9  mov     [rsp+38h+var_18], 0
0x180052dc1  lea     rdx, aMicrosoftWindo; "microsoft^windows^spellchecking^host"
0x180052dc8  xor     r9d, r9d
0x180052dcb  lea     rcx, aMicrosoftWindo; "microsoft^windows^spellchecking^host"
0x180052dd2  call    cs:__imp_CreateAppContainerProfile
0x180052dd8  cmp     eax, 800700B7h
0x180052ddd  jnz     short loc_180052DEF
0x180052ddf  mov     rdx, rbx
0x180052de2  lea     rcx, aMicrosoftWindo; "microsoft^windows^spellchecking^host"
0x180052de9  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x180052def  add     rsp, 30h
0x180052df3  pop     rbx
0x180052df4  retn
```
