# _This<CWorkspaceSetupMessagePage2>(ushort const *,HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18001cc94`
- end: `0x18001cceb`
- name: `??$_This@VCWorkspaceSetupMessagePage2@@@@YAPEAVCWorkspaceSetupMessagePage2@@PEBGPEAUHWND__@@I_K_J@Z`
- size: `87`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpString@<rcx>, HWND hWnd@<rdx>, HANDLE hData)`
- caller_count: `12`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001d1bc`
- `0x18001d250`
- `0x18001daa0`
- `0x18001e330`
- `0x180020374`
- `0x180020460`
- `0x1800213d8`
- `0x180021480`
- `0x180022228`
- `0x180022300`
- `0x180022f1c`
- `0x180023000`

## callees

- `0x18001cc94`

## import_xrefs

- `USER32!GetPropW` at `0x18001ccd9`
- `USER32!GetPropW` at `0x18001ccd9`
- `USER32!RemovePropW` at `0x18001ccd1`
- `USER32!RemovePropW` at `0x18001ccd1`
- `USER32!SetPropW` at `0x18001ccbd`
- `USER32!SetPropW` at `0x18001ccbd`

## pseudocode

```c
HANDLE __fastcall _This<CWorkspaceSetupMessagePage2>(LPCWSTR lpString, HWND hWnd, int a3, __int64 a4, _QWORD *hData)
{
  HANDLE v5; // rbx

  if ( a3 == 272 )
  {
    v5 = hData;
    if ( *(_DWORD *)hData == 104 )
      v5 = (HANDLE)hData[6];
    SetPropW(hWnd, lpString, v5);
  }
  else if ( a3 == 2 )
  {
    return RemovePropW(hWnd, lpString);
  }
  else
  {
    return GetPropW(hWnd, lpString);
  }
  return v5;
}

```

## disassembly

```asm
0x18001cc94  push    rbx
0x18001cc96  sub     rsp, 20h
0x18001cc9a  mov     rax, rdx
0x18001cc9d  cmp     r8d, 110h
0x18001cca4  jnz     short loc_18001CCC5
0x18001cca6  mov     rbx, [rsp+28h+hData]
0x18001ccab  cmp     dword ptr [rbx], 68h ; 'h'
0x18001ccae  jnz     short loc_18001CCB4
0x18001ccb0  mov     rbx, [rbx+30h]
0x18001ccb4  mov     rdx, rcx; lpString
0x18001ccb7  mov     r8, rbx; hData
0x18001ccba  mov     rcx, rax; hWnd
0x18001ccbd  call    cs:__imp_SetPropW
0x18001ccc3  jmp     short loc_18001CCE2
0x18001ccc5  mov     rdx, rcx; lpString
0x18001ccc8  mov     rcx, rax; hWnd
0x18001cccb  cmp     r8d, 2
0x18001cccf  jnz     short loc_18001CCD9
0x18001ccd1  call    cs:__imp_RemovePropW
0x18001ccd7  jmp     short loc_18001CCDF
0x18001ccd9  call    cs:__imp_GetPropW
0x18001ccdf  mov     rbx, rax
0x18001cce2  mov     rax, rbx
0x18001cce5  add     rsp, 20h
0x18001cce9  pop     rbx
0x18001ccea  retn
```
