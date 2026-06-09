# PortListInsertRequest

- ea: `0x14000acd0`
- end: `0x14000ae01`
- name: `PortListInsertRequest`
- size: `305`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140006040`
- `0x140006a70`
- `0x14000ac24`

## callees

- `0x14000acd0`

## pseudocode

```c
__int64 __fastcall PortListInsertRequest(__int64 a1, _QWORD *a2)
{
  int v4; // ecx
  _QWORD *j; // rax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // r9
  __int64 result; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *i; // rdx
  int v15; // r9d

  v4 = *(_DWORD *)(a1 + 48);
  if ( v4 )
  {
    if ( v4 == 2 )
    {
      for ( i = *(_QWORD **)a1; i != (_QWORD *)a1; i = (_QWORD *)*i )
      {
        v15 = 0;
        while ( *((_DWORD *)a2 + (unsigned int)(1 - v15) + 4) == *((_DWORD *)i + (unsigned int)(1 - v15) + 4) )
        {
          if ( (unsigned int)++v15 >= 2 )
          {
            if ( v15 == 2 )
              goto LABEL_27;
            break;
          }
        }
        if ( *((_DWORD *)a2 + (unsigned int)(1 - v15) + 4) <= *((_DWORD *)i + (unsigned int)(1 - v15) + 4) )
          break;
LABEL_27:
        ;
      }
      v13 = (_QWORD *)i[1];
      if ( (_QWORD *)*v13 == i )
      {
        *a2 = i;
        a2[1] = v13;
        *v13 = a2;
        i[1] = a2;
        *(_QWORD *)(a1 + 16) = *(_QWORD *)a1;
        goto LABEL_10;
      }
    }
    else
    {
      v12 = *(_QWORD **)(a1 + 8);
      if ( *v12 == a1 )
      {
        *a2 = a1;
        a2[1] = v12;
        *v12 = a2;
        *(_QWORD *)(a1 + 8) = a2;
        *(_QWORD *)(a1 + 16) = *(_QWORD *)a1;
        goto LABEL_10;
      }
    }
LABEL_15:
    __fastfail(3u);
  }
  for ( j = *(_QWORD **)a1; j != (_QWORD *)a1; j = (_QWORD *)*j )
  {
    if ( a2[2] < j[2] )
      break;
  }
  v6 = (_QWORD *)j[1];
  if ( (_QWORD *)*v6 != j )
    goto LABEL_15;
  *a2 = j;
  a2[1] = v6;
  *v6 = a2;
  j[1] = a2;
  v7 = *(_QWORD *)(a1 + 16);
  if ( v7 == a1 )
  {
    *(_QWORD *)(a1 + 16) = *(_QWORD *)a1;
  }
  else
  {
    v8 = *(_QWORD *)(a1 + 40);
    v9 = a2[2];
    if ( v9 >= v8 )
    {
      v10 = *(_QWORD *)(v7 + 16);
      if ( v9 < v10 || v10 < v8 )
        *(_QWORD *)(a1 + 16) = a2;
    }
  }
LABEL_10:
  result = *(_QWORD *)(a1 + 32);
  ++*(_DWORD *)(a1 + 24);
  if ( result )
    ++*(_DWORD *)(result + 4);
  return result;
}

```

## disassembly

```asm
0x14000acd0  mov     r8, rcx
0x14000acd3  mov     r10, rdx
0x14000acd6  mov     ecx, [rcx+30h]
0x14000acd9  test    ecx, ecx
0x14000acdb  jnz     loc_14000ADA1
0x14000ace1  mov     rax, [r8]
0x14000ace4  cmp     rax, r8
0x14000ace7  jz      short loc_14000ACFE
0x14000ace9  mov     rcx, [rdx+10h]
0x14000aced  nop     dword ptr [rax]
0x14000acf0  cmp     rcx, [rax+10h]
0x14000acf4  jb      short loc_14000ACFE
0x14000acf6  mov     rax, [rax]
0x14000acf9  cmp     rax, r8
0x14000acfc  jnz     short loc_14000ACF0
0x14000acfe  mov     rcx, [rax+8]
0x14000ad02  cmp     [rcx], rax
0x14000ad05  jnz     short loc_14000AD5A
0x14000ad07  mov     [rdx], rax
0x14000ad0a  mov     [rdx+8], rcx
0x14000ad0e  mov     [rcx], r10
0x14000ad11  mov     [rax+8], r10
0x14000ad15  mov     rdx, [r8+10h]
0x14000ad19  cmp     rdx, r8
0x14000ad1c  jz      short loc_14000AD4B
0x14000ad1e  mov     rcx, [r8+28h]
0x14000ad22  mov     rax, [r10+10h]
0x14000ad26  cmp     rax, rcx
0x14000ad29  jb      short loc_14000AD39
0x14000ad2b  mov     r9, [rdx+10h]
0x14000ad2f  cmp     rax, r9
0x14000ad32  jb      short loc_14000AD54
0x14000ad34  cmp     r9, rcx
0x14000ad37  jb      short loc_14000AD54
0x14000ad39  mov     rax, [r8+20h]
0x14000ad3d  inc     dword ptr [r8+18h]
0x14000ad41  test    rax, rax
0x14000ad44  jz      short locret_14000AD49
0x14000ad46  inc     dword ptr [rax+4]
0x14000ad49  retn
0x14000ad4b  mov     rax, [r8]
0x14000ad4e  mov     [r8+10h], rax
0x14000ad52  jmp     short loc_14000AD39
0x14000ad54  mov     [r8+10h], r10
0x14000ad58  jmp     short loc_14000AD39
0x14000ad5a  mov     ecx, 3
0x14000ad5f  int     29h; Win8: RtlFailFast(ecx)
0x14000ad61  mov     rax, [r8+8]
0x14000ad65  cmp     [rax], r8
0x14000ad68  jnz     short loc_14000AD5A
0x14000ad6a  mov     [rdx], r8
0x14000ad6d  mov     [rdx+8], rax
0x14000ad71  mov     [rax], r10
0x14000ad74  mov     [r8+8], r10
0x14000ad78  mov     rax, [r8]
0x14000ad7b  mov     [r8+10h], rax
0x14000ad7f  jmp     short loc_14000AD39
0x14000ad81  mov     rax, [rdx+8]
0x14000ad85  cmp     [rax], rdx
0x14000ad88  jnz     short loc_14000AD5A
0x14000ad8a  mov     [r10], rdx
0x14000ad8d  mov     [r10+8], rax
0x14000ad91  mov     [rax], r10
0x14000ad94  mov     [rdx+8], r10
0x14000ad98  mov     rax, [r8]
0x14000ad9b  mov     [r8+10h], rax
0x14000ad9f  jmp     short loc_14000AD39
0x14000ada1  sub     ecx, 1
0x14000ada4  jz      short loc_14000AD61
0x14000ada6  cmp     ecx, 1
0x14000ada9  jnz     short loc_14000AD61
0x14000adab  mov     rdx, [r8]
0x14000adae  cmp     rdx, r8
0x14000adb1  jz      short loc_14000AD81
0x14000adb3  xor     r9d, r9d
0x14000adb6  mov     eax, 1
0x14000adbb  sub     eax, r9d
0x14000adbe  lea     rcx, ds:0[rax*4]
0x14000adc6  mov     eax, [rcx+rdx+10h]
0x14000adca  cmp     [rcx+r10+10h], eax
0x14000adcf  jnz     short loc_14000ADDC
0x14000add1  inc     r9d
0x14000add4  cmp     r9d, 2
0x14000add8  jb      short loc_14000ADB6
0x14000adda  jz      short loc_14000ADF7
0x14000addc  mov     eax, 1
0x14000ade1  sub     eax, r9d
0x14000ade4  lea     rcx, ds:0[rax*4]
0x14000adec  mov     eax, [rcx+rdx+10h]
0x14000adf0  cmp     [rcx+r10+10h], eax
0x14000adf5  jbe     short loc_14000AD81
0x14000adf7  mov     rdx, [rdx]
0x14000adfa  cmp     rdx, r8
0x14000adfd  jnz     short loc_14000ADB3
0x14000adff  jmp     short loc_14000AD81
```
