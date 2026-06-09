# CommonUtil::UtilRegGetValueDword(HKEY__ *,ushort const *,ulong *)

- ea: `0x14000e648`
- end: `0x14000e6ad`
- name: `?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAK@Z`
- size: `101`
- prototype: `__int64 __fastcall(CommonUtil *this, HKEY, BYTE *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003188`

## callees

- `0x14000e35c`
- `0x14000e648`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegGetValueDword(CommonUtil *this, HKEY a2, BYTE *a3, unsigned int *a4)
{
  __int64 result; // rax
  DWORD v5; // [rsp+48h] [rbp+10h] BYREF
  int v6; // [rsp+4Ch] [rbp+14h]
  __int64 v7; // [rsp+58h] [rbp+20h] BYREF

  v6 = HIDWORD(a2);
  v5 = 0;
  v7 = 4;
  result = CommonUtil::UtilRegGetValue(this, (const WCHAR *)&stru_140012E78, &v5, (unsigned int *)&v7, a3);
  if ( (_DWORD)result == -2147024662 )
    return 2147944029LL;
  if ( (int)result >= 0 )
    return v5 != 4 ? 0x8007065D : 0;
  if ( (_DWORD)result == -2147024894 )
    return 2147942402LL;
  return result;
}

```

## disassembly

```asm
0x14000e648  mov     rax, rsp
0x14000e64b  mov     [rax+10h], rdx
0x14000e64f  sub     rsp, 38h
0x14000e653  mov     [rax-18h], r8
0x14000e657  lea     r9, [rax+20h]; unsigned int *
0x14000e65b  lea     r8, [rax+10h]; unsigned __int16 *
0x14000e65f  mov     dword ptr [rax+10h], 0
0x14000e666  lea     rdx, stru_140012E78; HKEY
0x14000e66d  mov     qword ptr [rax+20h], 4
0x14000e675  call    ?UtilRegGetValue@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAKPEA_KPEAX@Z; CommonUtil::UtilRegGetValue(HKEY__ *,ushort const *,ulong *,unsigned __int64 *,void *)
0x14000e67a  cmp     eax, 800700EAh
0x14000e67f  jz      short loc_14000E6A3
0x14000e681  test    eax, eax
0x14000e683  js      short loc_14000E697
0x14000e685  mov     eax, [rsp+38h+arg_8]
0x14000e689  sub     eax, 4
0x14000e68c  neg     eax
0x14000e68e  sbb     eax, eax
0x14000e690  and     eax, 8007065Dh
0x14000e695  jmp     short loc_14000E6A8
0x14000e697  mov     ecx, 80070002h
0x14000e69c  cmp     eax, ecx
0x14000e69e  cmovz   eax, ecx
0x14000e6a1  jmp     short loc_14000E6A8
0x14000e6a3  mov     eax, 8007065Dh
0x14000e6a8  add     rsp, 38h
0x14000e6ac  retn
```
