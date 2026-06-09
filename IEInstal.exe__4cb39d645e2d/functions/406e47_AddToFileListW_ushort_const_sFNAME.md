# AddToFileListW(ushort const *,sFNAME * *)

- ea: `0x406e47`
- end: `0x406e84`
- name: `?AddToFileListW@@YGJPBGPAPAUsFNAME@@@Z`
- size: `61`
- prototype: `HRESULT __fastcall(int, LPVOID **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x40373b`
- `0x403ffd`

## callees

- `0x406a93`
- `0x406d91`
- `0x406e47`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x406e78`
- `ole32!CoTaskMemFree` at `0x406e78`

## pseudocode

```c
HRESULT __fastcall AddToFileListW(int a1, LPVOID **a2)
{
  HRESULT v3; // esi
  const unsigned __int16 *v5; // [esp+0h] [ebp-Ch]
  char **v6; // [esp+4h] [ebp-8h]
  LPVOID pv; // [esp+8h] [ebp-4h] BYREF

  pv = 0;
  v3 = WSZtoSZ((unsigned int)&pv, v5, v6);
  if ( v3 >= 0 )
  {
    v3 = AddToFileListA((size_t)pv, a2);
    CoTaskMemFree(pv);
  }
  return v3;
}

```

## disassembly

```asm
0x406e47  mov     edi, edi
0x406e49  push    ebp
0x406e4a  mov     ebp, esp
0x406e4c  push    ecx
0x406e4d  push    esi; struct sFNAME **
0x406e4e  push    edi; char *
0x406e4f  lea     eax, [ebp+pv]
0x406e52  mov     [ebp+pv], 0
0x406e59  mov     edi, edx
0x406e5b  mov     edx, ecx
0x406e5d  push    eax; unsigned int
0x406e5e  call    ?WSZtoSZ@@YGJIPBGPAPAD@Z; WSZtoSZ(uint,ushort const *,char * *)
0x406e63  mov     esi, eax
0x406e65  test    esi, esi
0x406e67  js      short loc_406E7E
0x406e69  mov     ecx, [ebp+pv]
0x406e6c  mov     edx, edi
0x406e6e  call    ?AddToFileListA@@YGJPBDPAPAUsFNAME@@@Z; AddToFileListA(char const *,sFNAME * *)
0x406e73  push    [ebp+pv]; pv
0x406e76  mov     esi, eax
0x406e78  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x406e7e  pop     edi
0x406e7f  mov     eax, esi
0x406e81  pop     esi
0x406e82  leave
0x406e83  retn
```
