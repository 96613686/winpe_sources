# BCryptIumDereferenceObject(_BCRYPT_ISO_OBJECT *)

- ea: `0x140002080`
- end: `0x140002156`
- name: `?BCryptIumDereferenceObject@@YAXPEAU_BCRYPT_ISO_OBJECT@@@Z`
- size: `214`
- prototype: `void __fastcall(HLOCAL hMem)`
- caller_count: `23`
- callee_count: `4`
- tags: ``

## callers

- `0x140002390`
- `0x140002620`
- `0x140008538`
- `0x14000cd48`
- `0x14000e370`
- `0x14000e510`
- `0x14000e830`
- `0x14000ea40`
- `0x14000ec10`
- `0x14000ed50`
- `0x14000ee90`
- `0x14000f0d0`
- `0x14000f300`
- `0x14000f520`
- `0x14000fc50`
- `0x14000fe40`
- `0x1400100d0`
- `0x1400106a0`
- `0x140010b50`
- `0x140010cd0`
- `0x1400110a0`
- `0x1400113a0`
- `0x140011730`

## callees

- `0x140002080`
- `0x1400097c0`
- `0x14001193c`
- `0x140011964`

## pseudocode

```c
void __fastcall BCryptIumDereferenceObject(volatile signed __int32 *hMem)
{
  PVOID *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // r9

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hMem )
  {
    v4 = (unsigned int)_InterlockedDecrement(hMem + 8);
    if ( (_DWORD)v4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, v4);
    }
    else
    {
      FreeBCryptIsoObject((HLOCAL)hMem);
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v3 = 20;
        goto LABEL_8;
      }
    }
  }
  else if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 )
  {
    v3 = 19;
LABEL_8:
    WPP_SF_(v2[2], v3, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids);
  }
}

```

## disassembly

```asm
0x140002080  mov     [rsp+arg_0], rbx
0x140002085  push    rdi
0x140002086  sub     rsp, 20h
0x14000208a  mov     rbx, rcx
0x14000208d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002094  lea     rdi, WPP_GLOBAL_Control
0x14000209b  cmp     rcx, rdi
0x14000209e  jz      short loc_1400020C2
0x1400020a0  test    byte ptr [rcx+1Ch], 4
0x1400020a4  jz      short loc_1400020C2
0x1400020a6  mov     rcx, [rcx+10h]
0x1400020aa  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x1400020b1  mov     edx, 12h
0x1400020b6  call    WPP_SF_
0x1400020bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020c2  test    rbx, rbx
0x1400020c5  jnz     short loc_1400020F1
0x1400020c7  cmp     rcx, rdi
0x1400020ca  jz      short loc_14000214B
0x1400020cc  test    byte ptr [rcx+1Ch], 4
0x1400020d0  jz      short loc_14000214B
0x1400020d2  mov     edx, 13h
0x1400020d7  mov     rcx, [rcx+10h]
0x1400020db  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x1400020e2  mov     rbx, [rsp+28h+arg_0]
0x1400020e7  add     rsp, 20h
0x1400020eb  pop     rdi
0x1400020ec  jmp     WPP_SF_
0x1400020f1  mov     r9d, 0FFFFFFFFh
0x1400020f7  lock xadd [rbx+20h], r9d
0x1400020fd  sub     r9d, 1
0x140002101  jnz     short loc_140002124
0x140002103  mov     rcx, rbx; hMem
0x140002106  call    ?FreeBCryptIsoObject@@YAXPEAU_BCRYPT_ISO_OBJECT@@@Z; FreeBCryptIsoObject(_BCRYPT_ISO_OBJECT *)
0x14000210b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002112  cmp     rcx, rdi
0x140002115  jz      short loc_14000214B
0x140002117  test    byte ptr [rcx+1Ch], 4
0x14000211b  jz      short loc_14000214B
0x14000211d  mov     edx, 14h
0x140002122  jmp     short loc_1400020D7
0x140002124  mov     rcx, cs:WPP_GLOBAL_Control
0x14000212b  cmp     rcx, rdi
0x14000212e  jz      short loc_14000214B
0x140002130  test    byte ptr [rcx+1Ch], 4
0x140002134  jz      short loc_14000214B
0x140002136  mov     rcx, [rcx+10h]
0x14000213a  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x140002141  mov     edx, 15h
0x140002146  call    WPP_SF_d
0x14000214b  mov     rbx, [rsp+28h+arg_0]
0x140002150  add     rsp, 20h
0x140002154  pop     rdi
0x140002155  retn
```
