# RasRequestNotification

- ea: `0x18001dde0`
- end: `0x18001df21`
- name: `RasRequestNotification`
- size: `321`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001dde0`
- `0x180021000`
- `0x1800219f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001de64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001de64`

## pseudocode

```c
__int64 __fastcall RasRequestNotification(__int64 a1, __int64 a2, __int64 a3)
{
  PVOID *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  DWORD CurrentProcessId; // eax
  DWORD v9; // esi
  unsigned int v10; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 281, a3, a1, a2);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    v6 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 282;
LABEL_24:
      WPP_SF_d(v5[2], v7, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
      return v6;
    }
    return v6;
  }
  CurrentProcessId = GetCurrentProcessId();
  v9 = CurrentProcessId;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      283,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  v10 = SubmitLocalRequest(0x1Eu, a1, a2, v9);
  v6 = v10;
  if ( v10 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_20;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 284, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 6u )
  {
    v7 = 285;
    goto LABEL_24;
  }
  return v6;
}

```

## disassembly

```asm
0x18001dde0  push    rbx
0x18001dde2  push    rsi
0x18001dde3  push    rdi
0x18001dde4  push    r14
0x18001dde6  sub     rsp, 38h
0x18001ddea  mov     rdi, rdx
0x18001dded  mov     rbx, rcx
0x18001ddf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ddf7  lea     r14, WPP_GLOBAL_Control
0x18001ddfe  cmp     rcx, r14
0x18001de01  jz      short loc_18001DE25
0x18001de03  test    byte ptr [rcx+1Ch], 40h
0x18001de07  jz      short loc_18001DE25
0x18001de09  cmp     byte ptr [rcx+19h], 6
0x18001de0d  jb      short loc_18001DE25
0x18001de0f  mov     rcx, [rcx+10h]
0x18001de13  mov     edx, 119h
0x18001de18  mov     r9, rbx
0x18001de1b  mov     [rsp+58h+var_38], rdi
0x18001de20  call    WPP_SF_qq
0x18001de25  mov     rcx, rbx
0x18001de28  call    ValidatePortHandle
0x18001de2d  test    eax, eax
0x18001de2f  jnz     short loc_18001DE64
0x18001de31  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de38  mov     ebx, 259h
0x18001de3d  cmp     rcx, r14
0x18001de40  jz      loc_18001DF15
0x18001de46  test    byte ptr [rcx+1Ch], 40h
0x18001de4a  jz      loc_18001DF15
0x18001de50  cmp     byte ptr [rcx+19h], 2
0x18001de54  jb      loc_18001DF15
0x18001de5a  mov     edx, 11Ah
0x18001de5f  jmp     loc_18001DF02
0x18001de64  call    cs:__imp_GetCurrentProcessId
0x18001de6a  mov     esi, eax
0x18001de6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de73  cmp     rcx, r14
0x18001de76  jz      short loc_18001DE9C
0x18001de78  test    byte ptr [rcx+1Ch], 40h
0x18001de7c  jz      short loc_18001DE9C
0x18001de7e  cmp     byte ptr [rcx+19h], 5
0x18001de82  jb      short loc_18001DE9C
0x18001de84  mov     rcx, [rcx+10h]
0x18001de88  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001de8f  mov     edx, 11Bh
0x18001de94  mov     r9d, eax
0x18001de97  call    WPP_SF_d
0x18001de9c  mov     ecx, 1Eh
0x18001dea1  mov     r9d, esi
0x18001dea4  mov     r8, rdi
0x18001dea7  mov     rdx, rbx
0x18001deaa  call    SubmitLocalRequest
0x18001deaf  mov     ebx, eax
0x18001deb1  test    eax, eax
0x18001deb3  jz      short loc_18001DEE5
0x18001deb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001debc  cmp     rcx, r14
0x18001debf  jz      short loc_18001DF15
0x18001dec1  test    byte ptr [rcx+1Ch], 40h
0x18001dec5  jz      short loc_18001DEEC
0x18001dec7  cmp     byte ptr [rcx+19h], 2
0x18001decb  jb      short loc_18001DEEC
0x18001decd  mov     rcx, [rcx+10h]
0x18001ded1  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ded8  mov     edx, 11Ch
0x18001dedd  mov     r9d, eax
0x18001dee0  call    WPP_SF_d
0x18001dee5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001deec  cmp     rcx, r14
0x18001deef  jz      short loc_18001DF15
0x18001def1  test    byte ptr [rcx+1Ch], 40h
0x18001def5  jz      short loc_18001DF15
0x18001def7  cmp     byte ptr [rcx+19h], 6
0x18001defb  jb      short loc_18001DF15
0x18001defd  mov     edx, 11Dh
0x18001df02  mov     rcx, [rcx+10h]
0x18001df06  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001df0d  mov     r9d, ebx
0x18001df10  call    WPP_SF_d
0x18001df15  mov     eax, ebx
0x18001df17  add     rsp, 38h
0x18001df1b  pop     r14
0x18001df1d  pop     rdi
0x18001df1e  pop     rsi
0x18001df1f  pop     rbx
0x18001df20  retn
```
