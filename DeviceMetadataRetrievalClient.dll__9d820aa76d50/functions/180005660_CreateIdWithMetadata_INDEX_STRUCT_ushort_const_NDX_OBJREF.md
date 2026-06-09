# CreateIdWithMetadata(_INDEX_STRUCT *,ushort const *,NDX_OBJREF *)

- ea: `0x180005660`
- end: `0x180005751`
- name: `?CreateIdWithMetadata@@YAKPEAU_INDEX_STRUCT@@PEBGPEAUNDX_OBJREF@@@Z`
- size: `241`
- prototype: `unsigned int __fastcall(struct _INDEX_STRUCT *, const unsigned __int16 *, struct NDX_OBJREF *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800060d0`

## callees

- `0x180004dec`
- `0x180005660`
- `0x180013700`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800056a5`
- `KERNEL32!GetLastError` at `0x1800056f6`
- `KERNEL32!GetLastError` at `0x1800056a5`
- `KERNEL32!GetLastError` at `0x1800056f6`
- `DEVRTL!NdxTableRemoveObject` at `0x180005734`
- `DEVRTL!NdxTableRemoveObject` at `0x180005734`
- `DEVRTL!NdxTableAddObjectToList` at `0x1800056ec`
- `DEVRTL!NdxTableAddObjectToList` at `0x1800056ec`
- `DEVRTL!NdxTableAddObject` at `0x18000569b`
- `DEVRTL!NdxTableAddObject` at `0x18000569b`

## pseudocode

```c
__int64 __fastcall CreateIdWithMetadata(struct _INDEX_STRUCT *a1, const unsigned __int16 *a2, struct NDX_OBJREF *a3)
{
  __int64 v3; // rcx
  DWORD LastError; // eax
  DWORD v6; // ebx
  DWORD v8; // eax
  _OWORD v9[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+40h] [rbp-18h]

  v3 = *((_QWORD *)a1 + 5);
  v10 = 0;
  memset(v9, 0, sizeof(v9));
  if ( !(unsigned int)((__int64 (__fastcall *)(__int64, __int64, const unsigned __int16 *, _OWORD *))NdxTableAddObject)(
                        v3,
                        2,
                        a2,
                        v9) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, LastError);
    return v6;
  }
  if ( !(unsigned int)NdxTableAddObjectToList(v9, 0, a3) )
  {
    v8 = GetLastError();
    v6 = v8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, v8);
    NdxTableRemoveObject(v9);
    return v6;
  }
  return 0;
}

```

## disassembly

```asm
0x180005660  push    rbx
0x180005662  sub     rsp, 50h
0x180005666  mov     rax, cs:__security_cookie
0x18000566d  xor     rax, rsp
0x180005670  mov     [rsp+58h+var_10], rax
0x180005675  mov     rcx, [rcx+28h]
0x180005679  lea     r9, [rsp+58h+var_38]
0x18000567e  xor     eax, eax
0x180005680  xorps   xmm0, xmm0
0x180005683  mov     rbx, r8
0x180005686  mov     [rsp+58h+var_18], rax
0x18000568b  mov     r8, rdx
0x18000568e  movups  [rsp+58h+var_38], xmm0
0x180005693  lea     edx, [rax+2]
0x180005696  movups  [rsp+58h+var_28], xmm0
0x18000569b  call    cs:__imp_NdxTableAddObject
0x1800056a1  test    eax, eax
0x1800056a3  jnz     short loc_1800056E2
0x1800056a5  call    cs:__imp_GetLastError
0x1800056ab  mov     ebx, eax
0x1800056ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056b4  lea     rdx, WPP_GLOBAL_Control
0x1800056bb  cmp     rcx, rdx
0x1800056be  jz      short loc_1800056DE
0x1800056c0  test    byte ptr [rcx+1Ch], 1
0x1800056c4  jz      short loc_1800056DE
0x1800056c6  mov     rcx, [rcx+10h]
0x1800056ca  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x1800056d1  mov     edx, 0Dh
0x1800056d6  mov     r9d, eax
0x1800056d9  call    WPP_SF_d
0x1800056de  mov     eax, ebx
0x1800056e0  jmp     short loc_18000573E
0x1800056e2  mov     r8, rbx
0x1800056e5  lea     rcx, [rsp+58h+var_38]
0x1800056ea  xor     edx, edx
0x1800056ec  call    cs:__imp_NdxTableAddObjectToList
0x1800056f2  test    eax, eax
0x1800056f4  jnz     short loc_18000573C
0x1800056f6  call    cs:__imp_GetLastError
0x1800056fc  mov     ebx, eax
0x1800056fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180005705  lea     rdx, WPP_GLOBAL_Control
0x18000570c  cmp     rcx, rdx
0x18000570f  jz      short loc_18000572F
0x180005711  test    byte ptr [rcx+1Ch], 1
0x180005715  jz      short loc_18000572F
0x180005717  mov     rcx, [rcx+10h]
0x18000571b  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x180005722  mov     edx, 0Eh
0x180005727  mov     r9d, eax
0x18000572a  call    WPP_SF_d
0x18000572f  lea     rcx, [rsp+58h+var_38]
0x180005734  call    cs:__imp_NdxTableRemoveObject
0x18000573a  jmp     short loc_1800056DE
0x18000573c  xor     eax, eax
0x18000573e  mov     rcx, [rsp+58h+var_10]
0x180005743  xor     rcx, rsp; StackCookie
0x180005746  call    __security_check_cookie
0x18000574b  add     rsp, 50h
0x18000574f  pop     rbx
0x180005750  retn
```
