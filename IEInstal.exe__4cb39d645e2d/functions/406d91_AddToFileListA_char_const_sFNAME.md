# AddToFileListA(char const *,sFNAME * *)

- ea: `0x406d91`
- end: `0x406e41`
- name: `?AddToFileListA@@YGJPBDPAPAUsFNAME@@@Z`
- size: `176`
- prototype: `HRESULT __fastcall(size_t, LPVOID **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x406e47`
- `0x406e8a`

## callees

- `0x406224`
- `0x406521`
- `0x406d91`
- `0x408373`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x406dcf`
- `ole32!CoTaskMemAlloc` at `0x406de3`
- `ole32!CoTaskMemAlloc` at `0x406dcf`
- `ole32!CoTaskMemAlloc` at `0x406de3`
- `ole32!CoTaskMemFree` at `0x406e18`
- `ole32!CoTaskMemFree` at `0x406e26`
- `ole32!CoTaskMemFree` at `0x406e18`
- `ole32!CoTaskMemFree` at `0x406e26`

## pseudocode

```c
HRESULT __fastcall AddToFileListA(size_t a1, LPVOID **a2)
{
  HRESULT v2; // edi
  SIZE_T v3; // ebx
  LPVOID *v4; // esi
  char *v5; // eax
  size_t v7; // [esp+0h] [ebp-18h]
  char *v8; // [esp+0h] [ebp-18h]
  size_t *v9; // [esp+4h] [ebp-14h]
  char psz[4]; // [esp+14h] [ebp-4h] BYREF

  *(_DWORD *)psz = 0;
  if ( !a1 )
    return -2147024809;
  v2 = StringLengthWorkerA(psz, v7, v9);
  if ( v2 >= 0 )
  {
    v3 = *(_DWORD *)psz + 1;
    v4 = (LPVOID *)CoTaskMemAlloc(0xCu);
    if ( !v4 )
      return -2147024882;
    *v4 = 0;
    v4[1] = 0;
    v4[2] = 0;
    v5 = (char *)CoTaskMemAlloc(v3);
    *v4 = v5;
    if ( v5 )
    {
      v2 = StringCchCopyA(v5, v3, a1);
      if ( v2 >= 0 )
      {
        AxiAdjustSlashToBackslashA(v8);
        if ( *a2 )
          v4[1] = *a2;
        *a2 = v4;
        return v2;
      }
      CoTaskMemFree(*v4);
    }
    else
    {
      v2 = -2147024882;
    }
    CoTaskMemFree(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x406d91  mov     edi, edi
0x406d93  push    ebp
0x406d94  mov     ebp, esp
0x406d96  sub     esp, 0Ch
0x406d99  push    ebx
0x406d9a  mov     eax, ecx
0x406d9c  mov     [ebp+var_C], edx
0x406d9f  mov     [ebp+cchDest], eax
0x406da2  mov     dword ptr [ebp+psz], 0
0x406da9  push    esi; pcchLength
0x406daa  push    edi; char *
0x406dab  test    eax, eax
0x406dad  jz      loc_406E35
0x406db3  lea     ecx, [ebp+psz]
0x406db6  mov     edx, 104h
0x406dbb  push    ecx; psz
0x406dbc  mov     ecx, eax
0x406dbe  call    StringLengthWorkerA
0x406dc3  mov     edi, eax
0x406dc5  test    edi, edi
0x406dc7  js      short loc_406E3A
0x406dc9  mov     ebx, dword ptr [ebp+psz]
0x406dcc  push    0Ch; cb
0x406dce  inc     ebx
0x406dcf  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x406dd5  mov     esi, eax
0x406dd7  test    esi, esi
0x406dd9  jz      short loc_406E2E
0x406ddb  mov     edi, esi
0x406ddd  xor     eax, eax
0x406ddf  push    ebx; cb
0x406de0  stosd
0x406de1  stosd
0x406de2  stosd
0x406de3  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x406de9  mov     [esi], eax
0x406deb  test    eax, eax
0x406ded  jz      short loc_406E20
0x406def  push    [ebp+cchDest]; cchDest
0x406df2  push    ebx; unsigned int
0x406df3  push    eax; char *
0x406df4  call    ?StringCchCopyA@@YGJPADIPBD@Z; StringCchCopyA(char *,uint,char const *)
0x406df9  mov     edi, eax
0x406dfb  test    edi, edi
0x406dfd  js      short loc_406E16
0x406dff  mov     ecx, [esi]
0x406e01  call    ?AxiAdjustSlashToBackslashA@@YGXPAD@Z; AxiAdjustSlashToBackslashA(char *)
0x406e06  mov     ecx, [ebp+var_C]
0x406e09  mov     eax, [ecx]
0x406e0b  test    eax, eax
0x406e0d  jz      short loc_406E12
0x406e0f  mov     [esi+4], eax
0x406e12  mov     [ecx], esi
0x406e14  jmp     short loc_406E3A
0x406e16  push    dword ptr [esi]; pv
0x406e18  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x406e1e  jmp     short loc_406E25
0x406e20  mov     edi, 8007000Eh
0x406e25  push    esi; pv
0x406e26  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x406e2c  jmp     short loc_406E3A
0x406e2e  mov     edi, 8007000Eh
0x406e33  jmp     short loc_406E3A
0x406e35  mov     edi, 80070057h
0x406e3a  mov     eax, edi
0x406e3c  pop     edi
0x406e3d  pop     esi
0x406e3e  pop     ebx
0x406e3f  leave
0x406e40  retn
```
