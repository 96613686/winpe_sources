# CommonUtil::UtilRegGetValueDword(HKEY__ *,ushort const *,ulong *)

- ea: `0x14000fab4`
- end: `0x14000fb19`
- name: `?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAK@Z`
- size: `101`
- prototype: `__int64 __fastcall(CommonUtil *this, HKEY, BYTE *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005110`

## callees

- `0x14000f7d0`
- `0x14000fab4`

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
  result = CommonUtil::UtilRegGetValue(this, (const WCHAR *)&stru_140015648, &v5, (unsigned int *)&v7, a3);
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
0x14000fab4  mov     rax, rsp
0x14000fab7  mov     [rax+10h], rdx
0x14000fabb  sub     rsp, 38h
0x14000fabf  mov     [rax-18h], r8
0x14000fac3  lea     r9, [rax+20h]; unsigned int *
0x14000fac7  lea     r8, [rax+10h]; unsigned __int16 *
0x14000facb  mov     dword ptr [rax+10h], 0
0x14000fad2  lea     rdx, stru_140015648; HKEY
0x14000fad9  mov     qword ptr [rax+20h], 4
0x14000fae1  call    ?UtilRegGetValue@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAKPEA_KPEAX@Z; CommonUtil::UtilRegGetValue(HKEY__ *,ushort const *,ulong *,unsigned __int64 *,void *)
0x14000fae6  cmp     eax, 800700EAh
0x14000faeb  jz      short loc_14000FB0F
0x14000faed  test    eax, eax
0x14000faef  js      short loc_14000FB03
0x14000faf1  mov     eax, [rsp+38h+arg_8]
0x14000faf5  sub     eax, 4
0x14000faf8  neg     eax
0x14000fafa  sbb     eax, eax
0x14000fafc  and     eax, 8007065Dh
0x14000fb01  jmp     short loc_14000FB14
0x14000fb03  mov     ecx, 80070002h
0x14000fb08  cmp     eax, ecx
0x14000fb0a  cmovz   eax, ecx
0x14000fb0d  jmp     short loc_14000FB14
0x14000fb0f  mov     eax, 8007065Dh
0x14000fb14  add     rsp, 38h
0x14000fb18  retn
```
