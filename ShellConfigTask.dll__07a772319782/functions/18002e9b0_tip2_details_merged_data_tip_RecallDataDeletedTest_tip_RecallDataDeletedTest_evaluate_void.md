# tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::evaluate(void)

- ea: `0x18002e9b0`
- end: `0x18002eaee`
- name: `?evaluate@?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@EEAAXXZ`
- size: `318`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18002e9b0`

## string_xrefs

- `0x18002ea16`: `reason::failed_to_delete_snapshots_for_user`
- `0x18002ea5d`: `reason::failed_to_delete_recall_settings_for_user`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::evaluate(
        __int64 a1)
{
  int v1; // eax
  const char *v3; // rcx
  char v4; // al
  const char *v5; // r8
  __int64 result; // rax
  const char *v7; // rcx
  char v8; // al
  const char *v9; // r8
  char v10; // al
  const char *v11; // r9

  v1 = *(_DWORD *)(a1 + 280);
  if ( v1 == 1 )
  {
    v3 = "reason::failed_to_get_users";
    v4 = 114;
    v5 = "reason::failed_to_get_users";
    do
    {
      ++v3;
      if ( v4 == 58 )
        v5 = v3;
      v4 = *v3;
    }
    while ( *v3 );
    result = *(_QWORD *)(a1 + 264);
    if ( !*(_BYTE *)(result + 152) )
    {
      *(_WORD *)(result + 154) = 1;
LABEL_8:
      *(_BYTE *)(result + 152) = 3;
      *(_QWORD *)(result + 160) = v5;
    }
  }
  else if ( v1 == 2 )
  {
    v7 = "reason::failed_to_delete_snapshots_for_user";
    v8 = 114;
    v5 = "reason::failed_to_delete_snapshots_for_user";
    do
    {
      ++v7;
      if ( v8 == 58 )
        v5 = v7;
      v8 = *v7;
    }
    while ( *v7 );
    result = *(_QWORD *)(a1 + 264);
    if ( !*(_BYTE *)(result + 152) )
    {
      *(_WORD *)(result + 154) = 2;
      goto LABEL_8;
    }
  }
  else if ( *(_DWORD *)(a1 + 284) == 3 )
  {
    v9 = "reason::failed_to_delete_recall_settings_for_user";
    v10 = 114;
    v11 = "reason::failed_to_delete_recall_settings_for_user";
    do
    {
      ++v9;
      if ( v10 == 58 )
        v11 = v9;
      v10 = *v9;
    }
    while ( *v9 );
    result = *(_QWORD *)(a1 + 264);
    if ( !*(_BYTE *)(result + 152) )
    {
      *(_BYTE *)(result + 152) = 3;
      *(_WORD *)(result + 154) = 3;
      *(_QWORD *)(result + 160) = v11;
    }
  }
  else
  {
    result = *(_QWORD *)(a1 + 264);
    if ( (*(_DWORD *)(result + 56) & 0x200) != 0 )
    {
      if ( *(_BYTE *)(result + 152) )
        return result;
      *(_BYTE *)(result + 152) = 1;
      *(_WORD *)(result + 154) = 0x8000;
    }
    else
    {
      if ( *(_BYTE *)(result + 152) )
        return result;
      *(_BYTE *)(result + 152) = 3;
      *(_WORD *)(result + 154) = 16385;
    }
    *(_QWORD *)(result + 160) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002e9b0  mov     eax, [rcx+118h]
0x18002e9b6  mov     r10d, 1
0x18002e9bc  mov     rdx, rcx
0x18002e9bf  cmp     eax, r10d
0x18002e9c2  jnz     short loc_18002EA0B
0x18002e9c4  lea     rcx, aReasonFailedTo_2; "reason::failed_to_get_users"
0x18002e9cb  mov     al, 72h ; 'r'
0x18002e9cd  mov     r8, rcx
0x18002e9d0  add     rcx, r10
0x18002e9d3  cmp     al, 3Ah ; ':'
0x18002e9d5  jnz     short loc_18002E9DA
0x18002e9d7  mov     r8, rcx
0x18002e9da  mov     al, [rcx]
0x18002e9dc  test    al, al
0x18002e9de  jnz     short loc_18002E9D0
0x18002e9e0  mov     rax, [rdx+108h]
0x18002e9e7  cmp     byte ptr [rax+98h], 0
0x18002e9ee  jnz     locret_18002EAED
0x18002e9f4  mov     [rax+9Ah], r10w
0x18002e9fc  mov     byte ptr [rax+98h], 3
0x18002ea03  mov     [rax+0A0h], r8
0x18002ea0a  retn
0x18002ea0b  mov     r9d, 2
0x18002ea11  cmp     eax, r9d
0x18002ea14  jnz     short loc_18002EA50
0x18002ea16  lea     rcx, aReasonFailedTo; "reason::failed_to_delete_snapshots_for_"...
0x18002ea1d  mov     al, 72h ; 'r'
0x18002ea1f  mov     r8, rcx
0x18002ea22  add     rcx, r10
0x18002ea25  cmp     al, 3Ah ; ':'
0x18002ea27  jnz     short loc_18002EA2C
0x18002ea29  mov     r8, rcx
0x18002ea2c  mov     al, [rcx]
0x18002ea2e  test    al, al
0x18002ea30  jnz     short loc_18002EA22
0x18002ea32  mov     rax, [rdx+108h]
0x18002ea39  cmp     byte ptr [rax+98h], 0
0x18002ea40  jnz     locret_18002EAED
0x18002ea46  mov     [rax+9Ah], r9w
0x18002ea4e  jmp     short loc_18002E9FC
0x18002ea50  mov     ecx, 3
0x18002ea55  cmp     [rdx+11Ch], ecx
0x18002ea5b  jnz     short loc_18002EA9F
0x18002ea5d  lea     r8, aReasonFailedTo_0; "reason::failed_to_delete_recall_setting"...
0x18002ea64  mov     al, 72h ; 'r'
0x18002ea66  mov     r9, r8
0x18002ea69  add     r8, r10
0x18002ea6c  cmp     al, 3Ah ; ':'
0x18002ea6e  jnz     short loc_18002EA73
0x18002ea70  mov     r9, r8
0x18002ea73  mov     al, [r8]
0x18002ea76  test    al, al
0x18002ea78  jnz     short loc_18002EA69
0x18002ea7a  mov     rax, [rdx+108h]
0x18002ea81  cmp     byte ptr [rax+98h], 0
0x18002ea88  jnz     short locret_18002EAED
0x18002ea8a  mov     [rax+98h], cl
0x18002ea90  mov     [rax+9Ah], cx
0x18002ea97  mov     [rax+0A0h], r9
0x18002ea9e  retn
0x18002ea9f  mov     rax, [rdx+108h]
0x18002eaa6  test    dword ptr [rax+38h], 200h
0x18002eaad  jnz     short loc_18002EAC9
0x18002eaaf  cmp     byte ptr [rax+98h], 0
0x18002eab6  jnz     short locret_18002EAED
0x18002eab8  mov     [rax+98h], cl
0x18002eabe  mov     word ptr [rax+9Ah], 4001h
0x18002eac7  jmp     short loc_18002EAE2
0x18002eac9  cmp     byte ptr [rax+98h], 0
0x18002ead0  jnz     short locret_18002EAED
0x18002ead2  mov     [rax+98h], r10b
0x18002ead9  mov     word ptr [rax+9Ah], 8000h
0x18002eae2  mov     qword ptr [rax+0A0h], 0
0x18002eaed  retn
```
