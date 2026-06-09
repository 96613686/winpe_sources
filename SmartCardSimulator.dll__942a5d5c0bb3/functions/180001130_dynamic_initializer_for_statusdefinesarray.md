# _dynamic_initializer_for__statusdefinesarray__

- ea: `0x180001130`
- end: `0x1800027e1`
- name: `_dynamic_initializer_for__statusdefinesarray__`
- size: `5809`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001130`

## string_xrefs

- `0x180001369`: `Warning: end of file or record reached before expected (size is less than command.maximumResponseSize)`
- `0x18000161e`: `Warning: file filled up by last write`
- `0x18000169b`: `Warning: command specific counter value=%SW2%`
- `0x18000194a`: `FAILURE: Security related issue SW1=%SW1% SW2=%SW2%`
- `0x180001c09`: `INVALID: command chaining not supported`
- `0x180001c75`: `INVALID: command not allowed SW1=%SW1% SW2=%SW2%`
- `0x180001cc6`: `APDU_INVALID_CMD_INCOMPATIBLE_COMMAND`
- `0x180001ce8`: `INVALID: command incompatible with file structure`
- `0x180001d39`: `APDU_INVALID_CMD_SECURITY_UNSATISFIED`
- `0x180001d5b`: `INVALID: security status not satisfied`
- `0x180001f27`: `INVALID: command not allowed - no current elementary file`
- `0x1800020f6`: `INVALID: incorrect paramters in command data field`
- `0x180002501`: `INVALID: file already exists`
- `0x180002552`: `APDU_INVALID_PARAM_DIRECTORY_EXISTS`
- `0x180002574`: `INVALID: directory file already exists`
- `0x18000265a`: `INVALID: command.maximumResponseSize field invalid should be: SW2=%SW2%`

## pseudocode

```c
char *dynamic_initializer_for__statusdefinesarray__()
{
  __int64 *v0; // rdx
  __int64 *i; // rax
  int v2; // ecx
  __int64 *v3; // rax
  int v4; // ecx
  __int64 *v5; // rax
  int v6; // ecx
  __int64 *v7; // rax
  int v8; // ecx
  __int64 *v9; // rax
  int v10; // ecx
  __int64 *v11; // rax
  int v12; // ecx
  __int64 *v13; // rax
  int v14; // ecx
  __int64 *v15; // rax
  int v16; // ecx
  __int64 *v17; // rax
  int v18; // ecx
  __int64 *v19; // rax
  int v20; // ecx
  __int64 *v21; // rax
  int v22; // ecx
  __int64 *v23; // rax
  int v24; // ecx
  __int64 *v25; // rax
  int v26; // ecx
  __int64 *v27; // rax
  int v28; // ecx
  __int64 *v29; // rax
  int v30; // ecx
  __int64 *v31; // rax
  int v32; // ecx
  __int64 *v33; // rax
  int v34; // ecx
  __int64 *v35; // rax
  int v36; // ecx
  __int64 *v37; // rax
  int v38; // ecx
  __int64 *v39; // rax
  int v40; // ecx
  __int64 *v41; // rax
  int v42; // ecx
  __int64 *v43; // rax
  int v44; // ecx
  __int64 *v45; // rax
  int v46; // ecx
  __int64 *v47; // rax
  int v48; // ecx
  __int64 *v49; // rax
  int v50; // ecx
  __int64 *v51; // rax
  int v52; // ecx
  __int64 *v53; // rax
  int v54; // ecx
  __int64 *v55; // rax
  int v56; // ecx
  __int64 *v57; // rax
  int v58; // ecx
  __int64 *v59; // rax
  int v60; // ecx
  __int64 *v61; // rax
  int v62; // ecx
  __int64 *v63; // rax
  int v64; // ecx
  __int64 *v65; // rax
  int v66; // ecx
  __int64 *v67; // rax
  int v68; // ecx
  __int64 *v69; // rax
  int v70; // ecx
  __int64 *v71; // rax
  int v72; // ecx
  __int64 *v73; // rax
  int v74; // ecx
  __int64 *v75; // rax
  int v76; // ecx
  __int64 *v77; // rax
  int v78; // ecx
  __int64 *v79; // rax
  int v80; // ecx
  __int64 *v81; // rax
  int v82; // ecx
  __int64 *v83; // rax
  int v84; // ecx
  __int64 *v85; // rax
  int v86; // ecx
  __int64 *v87; // rax
  int v88; // ecx
  __int64 *v89; // rax
  int v90; // ecx
  __int64 *v91; // rax
  int v92; // ecx
  __int64 *v93; // rax
  int v94; // ecx
  __int64 *v95; // rax
  int v96; // ecx
  __int64 *v97; // rax
  int v98; // ecx
  int v99; // eax
  char *result; // rax

  v0 = `ProcessField::make'::`2'::sw1fieldmap;
  for ( i = `ProcessField::make'::`2'::sw1fieldmap; i != (__int64 *)"NULL"; ++i )
  {
    if ( *(_BYTE *)i == 0x90 )
    {
      v2 = *((_DWORD *)i + 1);
      goto LABEL_7;
    }
  }
  v2 = 0;
LABEL_7:
  dword_1800754D4 = v2;
  *(_QWORD *)&xmmword_1800754E0 = "APDU_SUCCESS";
  byte_1800754D8 = 0;
  *((_QWORD *)&xmmword_1800754E0 + 1) = "";
  *(_QWORD *)&xmmword_1800754F0 = "Success:";
  *((_QWORD *)&xmmword_1800754F0 + 1) = "";
  v3 = `ProcessField::make'::`2'::sw1fieldmap;
  dword_1800754DC = 2;
  dword_180075504 = 0;
  byte_180075500 = 97;
  while ( v3 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v3 == 97 )
    {
      v4 = *((_DWORD *)v3 + 1);
      goto LABEL_13;
    }
    ++v3;
  }
  v4 = 0;
LABEL_13:
  dword_180075504 = v4;
  qword_180075510 = (__int64)"APDU_SUCCESS_MORE_DATA";
  byte_180075508 = 0;
  qword_180075518 = (__int64)"";
  qword_180075520 = (__int64)"Success: more data available value=%SW2%";
  qword_180075528 = (__int64)"";
  v5 = `ProcessField::make'::`2'::sw1fieldmap;
  dword_18007550C = 3;
  dword_180075534 = 0;
  byte_180075530 = 98;
  while ( v5 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v5 == 98 )
    {
      v6 = *((_DWORD *)v5 + 1);
      goto LABEL_19;
    }
    ++v5;
  }
  v6 = 0;
LABEL_19:
  dword_180075534 = v6;
  qword_180075540 = (__int64)"APDU_WARNING";
  byte_180075538 = 0;
  qword_180075548 = (__int64)"";
  qword_180075550 = (__int64)"Warning: non-volatile memory state not changed SW1=%SW1% SW2=%SW2%";
  qword_180075558 = (__int64)"";
  v7 = `ProcessField::make'::`2'::sw1fieldmap;
  dword_18007553C = 1;
  dword_180075564 = 0;
  byte_180075560 = 98;
  while ( v7 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v7 == 98 )
    {
      v8 = *((_DWORD *)v7 + 1);
      goto LABEL_25;
    }
    ++v7;
  }
  v8 = 0;
LABEL_25:
  dword_180075564 = v8;
  qword_180075570 = (__int64)"APDU_WARNING_CORRUPTED_RESULT";
  byte_180075568 = -127;
  qword_180075578 = (__int64)"";
  qword_180075580 = (__int64)"Warning: returned data may be corrupt";
  qword_180075588 = (__int64)"";
  v9 = `ProcessField::make'::`2'::sw1fieldmap;
  dword_18007556C = 4;
  dword_180075594 = 0;
  byte_180075590 = 98;
  while ( v9 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v9 == 98 )
    {
      v10 = *((_DWORD *)v9 + 1);
      goto LABEL_31;
    }
    ++v9;
  }
  v10 = 0;
LABEL_31:
  dword_180075594 = v10;
  qword_1800755A0 = (__int64)"APDU_WARNING_UNEXPECTED_END";
  qword_1800755A8 = (__int64)"";
  qword_1800755B0 = (__int64)"Warning: end of file or record reached before expected (size is less than command.maximumResponseSize)";
  qword_1800755B8 = (__int64)"";
  v11 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075598 = -126;
  dword_18007559C = 4;
  dword_1800755C4 = 0;
  byte_1800755C0 = 98;
  while ( v11 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v11 == 98 )
    {
      v12 = *((_DWORD *)v11 + 1);
      goto LABEL_37;
    }
    ++v11;
  }
  v12 = 0;
LABEL_37:
  dword_1800755C4 = v12;
  qword_1800755D0 = (__int64)"APDU_WARNING_SELECTED_FILE_DEACTIVATED";
  qword_1800755D8 = (__int64)"";
  qword_1800755E0 = (__int64)"Warning: selected file deactivated";
  qword_1800755E8 = (__int64)"";
  v13 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_1800755C8 = -125;
  dword_1800755CC = 4;
  dword_1800755F4 = 0;
  byte_1800755F0 = 98;
  while ( v13 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v13 == 98 )
    {
      v14 = *((_DWORD *)v13 + 1);
      goto LABEL_43;
    }
    ++v13;
  }
  v14 = 0;
LABEL_43:
  dword_1800755F4 = v14;
  qword_180075600 = (__int64)"APDU_WARNING_FCI_CORRUPTED";
  qword_180075608 = (__int64)"";
  qword_180075610 = (__int64)"Warning: file control information not correctly formatted";
  qword_180075618 = (__int64)"";
  v15 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_1800755F8 = -124;
  dword_1800755FC = 4;
  dword_180075624 = 0;
  byte_180075620 = 98;
  while ( v15 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v15 == 98 )
    {
      v16 = *((_DWORD *)v15 + 1);
      goto LABEL_49;
    }
    ++v15;
  }
  v16 = 0;
LABEL_49:
  dword_180075624 = v16;
  qword_180075630 = (__int64)"APDU_WARNING_SELECTED_FILE_TERMINATED";
  qword_180075638 = (__int64)"";
  qword_180075640 = (__int64)"Warning: selected file in termination state";
  qword_180075648 = (__int64)"";
  v17 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075628 = -123;
  dword_18007562C = 4;
  dword_180075654 = 0;
  byte_180075650 = 98;
  while ( v17 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v17 == 98 )
    {
      v18 = *((_DWORD *)v17 + 1);
      goto LABEL_55;
    }
    ++v17;
  }
  v18 = 0;
LABEL_55:
  dword_180075654 = v18;
  qword_180075660 = (__int64)"APDU_WARNING_NO_INPUT_AVAILABLE";
  byte_180075658 = -122;
  qword_180075668 = (__int64)"";
  qword_180075670 = (__int64)"Warning: no input data available from a sensor on the card";
  qword_180075678 = (__int64)"";
  v19 = `ProcessField::make'::`2'::sw1fieldmap;
  dword_18007565C = 4;
  dword_180075684 = 0;
  byte_180075680 = 99;
  while ( v19 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v19 == 99 )
    {
      v20 = *((_DWORD *)v19 + 1);
      goto LABEL_61;
    }
    ++v19;
  }
  v20 = 0;
LABEL_61:
  dword_180075684 = v20;
  qword_180075690 = (__int64)"APDU_WARNING_CHG";
  qword_180075698 = (__int64)"";
  qword_1800756A0 = (__int64)"Warning: non-volatile memory state changed SW1=%SW1% SW2=%SW2%";
  qword_1800756A8 = (__int64)"";
  v21 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075688 = 0;
  dword_18007568C = 1;
  dword_1800756B4 = 0;
  byte_1800756B0 = 99;
  while ( v21 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v21 == 99 )
    {
      v22 = *((_DWORD *)v21 + 1);
      goto LABEL_67;
    }
    ++v21;
  }
  v22 = 0;
LABEL_67:
  dword_1800756B4 = v22;
  qword_1800756C0 = (__int64)"APDU_WARNING_CHG_FILE_FULL";
  qword_1800756C8 = (__int64)"";
  qword_1800756D0 = (__int64)"Warning: file filled up by last write";
  qword_1800756D8 = (__int64)"";
  v23 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_1800756B8 = -127;
  dword_1800756BC = 4;
  dword_1800756E4 = 0;
  byte_1800756E0 = 99;
  while ( v23 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v23 == 99 )
    {
      v24 = *((_DWORD *)v23 + 1);
      goto LABEL_73;
    }
    ++v23;
  }
  v24 = 0;
LABEL_73:
  dword_1800756E4 = v24;
  qword_1800756F0 = (__int64)"APDU_WARNING_CHG_COUNTER";
  byte_1800756E8 = -64;
  qword_1800756F8 = (__int64)"";
  qword_180075700 = (__int64)"Warning: command specific counter value=%SW2%";
  qword_180075708 = (__int64)"";
  v25 = `ProcessField::make'::`2'::sw1fieldmap;
  dword_1800756EC = 5;
  dword_180075714 = 0;
  byte_180075710 = 100;
  while ( v25 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v25 == 100 )
    {
      v26 = *((_DWORD *)v25 + 1);
      goto LABEL_79;
    }
    ++v25;
  }
  v26 = 0;
LABEL_79:
  dword_180075714 = v26;
  qword_180075720 = (__int64)"APDU_FAILURE";
  qword_180075728 = (__int64)"";
  qword_180075730 = (__int64)"FAILURE: execution error - non-volatile memory state not changed ";
  qword_180075738 = (__int64)"";
  v27 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075718 = 0;
  dword_18007571C = 2;
  dword_180075744 = 0;
  byte_180075740 = 100;
  while ( v27 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v27 == 100 )
    {
      v28 = *((_DWORD *)v27 + 1);
      goto LABEL_85;
    }
    ++v27;
  }
  v28 = 0;
LABEL_85:
  dword_180075744 = v28;
  qword_180075750 = (__int64)"APDU_FAILURE_DEFAULT";
  qword_180075758 = (__int64)"";
  qword_180075760 = (__int64)"FAILURE: non-volatile memory state not changed SW1=%SW1% SW2=%SW2%";
  qword_180075768 = (__int64)"";
  v29 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075748 = 0;
  dword_18007574C = 1;
  dword_180075774 = 0;
  byte_180075770 = 100;
  while ( v29 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v29 == 100 )
    {
      v30 = *((_DWORD *)v29 + 1);
      goto LABEL_91;
    }
    ++v29;
  }
  v30 = 0;
LABEL_91:
  dword_180075774 = v30;
  qword_180075780 = (__int64)"APDU_FAILURE_RESPONSE_REQUIRED";
  qword_180075788 = (__int64)"";
  qword_180075790 = (__int64)"FAILURE: immediate response required by the card";
  qword_180075798 = (__int64)"";
  v31 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075778 = 1;
  dword_18007577C = 4;
  dword_1800757A4 = 0;
  byte_1800757A0 = 101;
  while ( v31 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v31 == 101 )
    {
      v32 = *((_DWORD *)v31 + 1);
      goto LABEL_97;
    }
    ++v31;
  }
  v32 = 0;
LABEL_97:
  dword_1800757A4 = v32;
  qword_1800757B0 = (__int64)"APDU_FAILURE_CHG_DEFAULT";
  qword_1800757B8 = (__int64)"";
  qword_1800757C0 = (__int64)"FAILURE: non-volatile memory state changed SW1=%SW1% SW2=%SW2%";
  qword_1800757C8 = (__int64)"";
  v33 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_1800757A8 = 0;
  dword_1800757AC = 1;
  dword_1800757D4 = 0;
  byte_1800757D0 = 101;
  while ( v33 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v33 == 101 )
    {
      v34 = *((_DWORD *)v33 + 1);
      goto LABEL_103;
    }
    ++v33;
  }
  v34 = 0;
LABEL_103:
  dword_1800757D4 = v34;
  qword_1800757E0 = (__int64)"APDU_FAILURE_CHG_MEMORY_FAILURE";
  qword_1800757E8 = (__int64)"";
  qword_1800757F0 = (__int64)"FAILURE: memory failure";
  qword_1800757F8 = (__int64)"";
  v35 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_1800757D8 = -127;
  dword_1800757DC = 4;
  dword_180075804 = 0;
  byte_180075800 = 102;
  while ( v35 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v35 == 102 )
    {
      v36 = *((_DWORD *)v35 + 1);
      goto LABEL_109;
    }
    ++v35;
  }
  v36 = 0;
LABEL_109:
  dword_180075804 = v36;
  qword_180075810 = (__int64)"APDU_FAILURE_SEC_DEFAULT";
  qword_180075818 = (__int64)"";
  qword_180075820 = (__int64)"FAILURE: Security related issue SW1=%SW1% SW2=%SW2%";
  qword_180075828 = (__int64)"";
  v37 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075808 = 0;
  dword_18007580C = 1;
  dword_180075834 = 0;
  byte_180075830 = 103;
  while ( v37 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v37 == 103 )
    {
      v38 = *((_DWORD *)v37 + 1);
      goto LABEL_115;
    }
    ++v37;
  }
  v38 = 0;
LABEL_115:
  dword_180075834 = v38;
  qword_180075840 = (__int64)"APDU_INVALID_LENGTH";
  byte_180075838 = 0;
  qword_180075848 = (__int64)"";
  qword_180075850 = (__int64)"INVALID: Wrong length SW1=%SW1% SW2=%SW2%";
  qword_180075858 = (__int64)"";
  v39 = `ProcessField::make'::`2'::sw1fieldmap;
  dword_18007583C = 2;
  dword_180075864 = 0;
  byte_180075860 = 104;
  while ( v39 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v39 == 104 )
    {
      v40 = *((_DWORD *)v39 + 1);
      goto LABEL_121;
    }
    ++v39;
  }
  v40 = 0;
LABEL_121:
  dword_180075864 = v40;
  qword_180075870 = (__int64)"APDU_INVALID_CLA_DEFAULT";
  qword_180075878 = (__int64)"";
  qword_180075880 = (__int64)"INVALID: fields in CLA are not supported SW1=%SW1% SW2=%SW2%";
  qword_180075888 = (__int64)"";
  v41 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075868 = 0;
  dword_18007586C = 1;
  dword_180075894 = 0;
  byte_180075890 = 104;
  while ( v41 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v41 == 104 )
    {
      v42 = *((_DWORD *)v41 + 1);
      goto LABEL_127;
    }
    ++v41;
  }
  v42 = 0;
LABEL_127:
  dword_180075894 = v42;
  qword_1800758A0 = (__int64)"APDU_INVALID_CLA_CHANNEL_UNSUPPORTED";
  qword_1800758A8 = (__int64)"";
  qword_1800758B0 = (__int64)"INVALID: logical channel not supported";
  qword_1800758B8 = (__int64)"";
  v43 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075898 = -127;
  dword_18007589C = 4;
  dword_1800758C4 = 0;
  byte_1800758C0 = 104;
  while ( v43 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v43 == 104 )
    {
      v44 = *((_DWORD *)v43 + 1);
      goto LABEL_133;
    }
    ++v43;
  }
  v44 = 0;
LABEL_133:
  dword_1800758C4 = v44;
  qword_1800758D0 = (__int64)"APDU_INVALID_CLA_SECURE_MESSAGING_UNSUPPORTED";
  qword_1800758D8 = (__int64)"";
  qword_1800758E0 = (__int64)"INVALID: secure messaging not supported";
  qword_1800758E8 = (__int64)"";
  v45 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_1800758C8 = -126;
  dword_1800758CC = 4;
  dword_1800758F4 = 0;
  byte_1800758F0 = 104;
  while ( v45 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v45 == 104 )
    {
      v46 = *((_DWORD *)v45 + 1);
      goto LABEL_139;
    }
    ++v45;
  }
  v46 = 0;
LABEL_139:
  dword_1800758F4 = v46;
  qword_180075900 = (__int64)"APDU_INVALID_CLA_EXPECTED_LAST_MESSAGE_IN_CHAIN";
  qword_180075908 = (__int64)"";
  qword_180075910 = (__int64)"INVALID: last message of the chain expected";
  qword_180075918 = (__int64)"";
  v47 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_1800758F8 = -125;
  dword_1800758FC = 4;
  dword_180075924 = 0;
  byte_180075920 = 104;
  while ( v47 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v47 == 104 )
    {
      v48 = *((_DWORD *)v47 + 1);
      goto LABEL_145;
    }
    ++v47;
  }
  v48 = 0;
LABEL_145:
  dword_180075924 = v48;
  qword_180075930 = (__int64)"APDU_INVALID_CLA_CHAINING_UNSUPPORTED";
  byte_180075928 = -124;
  qword_180075938 = (__int64)"";
  qword_180075940 = (__int64)"INVALID: command chaining not supported";
  qword_180075948 = (__int64)"";
  v49 = `ProcessField::make'::`2'::sw1fieldmap;
  dword_18007592C = 4;
  dword_180075954 = 0;
  byte_180075950 = 105;
  while ( v49 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v49 == 105 )
    {
      v50 = *((_DWORD *)v49 + 1);
      goto LABEL_151;
    }
    ++v49;
  }
  v50 = 0;
LABEL_151:
  dword_180075954 = v50;
  qword_180075960 = (__int64)"APDU_INVALID_CMD_DEFAULT";
  qword_180075968 = (__int64)"";
  qword_180075970 = (__int64)"INVALID: command not allowed SW1=%SW1% SW2=%SW2%";
  qword_180075978 = (__int64)"";
  v51 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075958 = 0;
  dword_18007595C = 1;
  dword_180075984 = 0;
  byte_180075980 = 105;
  while ( v51 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v51 == 105 )
    {
      v52 = *((_DWORD *)v51 + 1);
      goto LABEL_157;
    }
    ++v51;
  }
  v52 = 0;
LABEL_157:
  dword_180075984 = v52;
  qword_180075990 = (__int64)"APDU_INVALID_CMD_INCOMPATIBLE_COMMAND";
  qword_180075998 = (__int64)"";
  qword_1800759A0 = (__int64)"INVALID: command incompatible with file structure";
  qword_1800759A8 = (__int64)"";
  v53 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075988 = -127;
  dword_18007598C = 4;
  dword_1800759B4 = 0;
  byte_1800759B0 = 105;
  while ( v53 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v53 == 105 )
    {
      v54 = *((_DWORD *)v53 + 1);
      goto LABEL_163;
    }
    ++v53;
  }
  v54 = 0;
LABEL_163:
  dword_1800759B4 = v54;
  qword_1800759C0 = (__int64)"APDU_INVALID_CMD_SECURITY_UNSATISFIED";
  qword_1800759C8 = (__int64)"";
  qword_1800759D0 = (__int64)"INVALID: security status not satisfied";
  qword_1800759D8 = (__int64)"";
  v55 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_1800759B8 = -126;
  dword_1800759BC = 4;
  dword_1800759E4 = 0;
  byte_1800759E0 = 105;
  while ( v55 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v55 == 105 )
    {
      v56 = *((_DWORD *)v55 + 1);
      goto LABEL_169;
    }
    ++v55;
  }
  v56 = 0;
LABEL_169:
  dword_1800759E4 = v56;
  qword_1800759F0 = (__int64)"APDU_INVALID_CMD_AUTH_METHOD_BLOCKED";
  qword_1800759F8 = (__int64)"";
  qword_180075A00 = (__int64)"INVALID: authentication method blocked";
  qword_180075A08 = (__int64)"";
  v57 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_1800759E8 = -125;
  dword_1800759EC = 4;
  dword_180075A14 = 0;
  byte_180075A10 = 105;
  while ( v57 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v57 == 105 )
    {
      v58 = *((_DWORD *)v57 + 1);
      goto LABEL_175;
    }
    ++v57;
  }
  v58 = 0;
LABEL_175:
  dword_180075A14 = v58;
  qword_180075A20 = (__int64)"APDU_INVALID_CMD_DATA_UNUSABLE";
  qword_180075A28 = (__int64)"";
  qword_180075A30 = (__int64)"INVALID: reference data not usable";
  qword_180075A38 = (__int64)"";
  v59 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075A18 = -124;
  dword_180075A1C = 4;
  dword_180075A44 = 0;
  byte_180075A40 = 105;
  while ( v59 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v59 == 105 )
    {
      v60 = *((_DWORD *)v59 + 1);
      goto LABEL_181;
    }
    ++v59;
  }
  v60 = 0;
LABEL_181:
  dword_180075A44 = v60;
  qword_180075A50 = (__int64)"APDU_INVALID_CMD_CONDITIONS_UNSATISFIED";
  qword_180075A58 = (__int64)"";
  qword_180075A60 = (__int64)"INVALID: conditions of use not satisfied";
  qword_180075A68 = (__int64)"";
  v61 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075A48 = -123;
  dword_180075A4C = 4;
  dword_180075A74 = 0;
  byte_180075A70 = 105;
  while ( v61 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v61 == 105 )
    {
      v62 = *((_DWORD *)v61 + 1);
      goto LABEL_187;
    }
    ++v61;
  }
  v62 = 0;
LABEL_187:
  dword_180075A74 = v62;
  qword_180075A80 = (__int64)"APDU_INVALID_CMD_NO_CURRENT_EF";
  qword_180075A88 = (__int64)"";
  qword_180075A90 = (__int64)"INVALID: command not allowed - no current elementary file";
  qword_180075A98 = (__int64)"";
  v63 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075A78 = -122;
  dword_180075A7C = 4;
  dword_180075AA4 = 0;
  byte_180075AA0 = 105;
  while ( v63 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v63 == 105 )
    {
      v64 = *((_DWORD *)v63 + 1);
      goto LABEL_193;
    }
    ++v63;
  }
  v64 = 0;
LABEL_193:
  dword_180075AA4 = v64;
  qword_180075AB0 = (__int64)"APDU_INVALID_CMD_SM_DO_MISSING";
  qword_180075AB8 = (__int64)"";
  qword_180075AC0 = (__int64)"INVALID: expected secure messaging data objects missing";
  qword_180075AC8 = (__int64)"";
  v65 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075AA8 = -121;
  dword_180075AAC = 4;
  dword_180075AD4 = 0;
  byte_180075AD0 = 105;
  while ( v65 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v65 == 105 )
    {
      v66 = *((_DWORD *)v65 + 1);
      goto LABEL_199;
    }
    ++v65;
  }
  v66 = 0;
LABEL_199:
  dword_180075AD4 = v66;
  qword_180075AE0 = (__int64)"APDU_INVALID_CMD_SM_DO_CORRUPT";
  byte_180075AD8 = -120;
  qword_180075AE8 = (__int64)"";
  qword_180075AF0 = (__int64)"INVALID: incorrect secure messaging data objects";
  qword_180075AF8 = (__int64)"";
  v67 = `ProcessField::make'::`2'::sw1fieldmap;
  dword_180075ADC = 4;
  dword_180075B04 = 0;
  byte_180075B00 = 106;
  while ( v67 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v67 == 106 )
    {
      v68 = *((_DWORD *)v67 + 1);
      goto LABEL_205;
    }
    ++v67;
  }
  v68 = 0;
LABEL_205:
  dword_180075B04 = v68;
  qword_180075B10 = (__int64)"APDU_INVALID_PARAM_DEFAULT";
  qword_180075B18 = (__int64)"";
  qword_180075B20 = (__int64)"INVALID: wrong parameters P1=%P1% P2=%P2% SW1=%SW1% SW2=%SW2%";
  qword_180075B28 = (__int64)"";
  v69 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075B08 = 0;
  dword_180075B0C = 1;
  dword_180075B34 = 0;
  byte_180075B30 = 106;
  while ( v69 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v69 == 106 )
    {
      v70 = *((_DWORD *)v69 + 1);
      goto LABEL_211;
    }
    ++v69;
  }
  v70 = 0;
LABEL_211:
  dword_180075B34 = v70;
  qword_180075B40 = (__int64)"APDU_INVALID_PARAM_DATA_FIELD";
  qword_180075B48 = (__int64)"";
  qword_180075B50 = (__int64)"INVALID: incorrect paramters in command data field";
  qword_180075B58 = (__int64)"";
  v71 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075B38 = 0x80;
  dword_180075B3C = 4;
  dword_180075B64 = 0;
  byte_180075B60 = 106;
  while ( v71 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v71 == 106 )
    {
      v72 = *((_DWORD *)v71 + 1);
      goto LABEL_217;
    }
    ++v71;
  }
  v72 = 0;
LABEL_217:
  dword_180075B64 = v72;
  qword_180075B70 = (__int64)"APDU_INVALID_PARAM_FUNCTION_UNSUPPORTED";
  qword_180075B78 = (__int64)"";
  qword_180075B80 = (__int64)"INVALID: function not supported";
  qword_180075B88 = (__int64)"";
  v73 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075B68 = -127;
  dword_180075B6C = 4;
  dword_180075B94 = 0;
  byte_180075B90 = 106;
  while ( v73 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v73 == 106 )
    {
      v74 = *((_DWORD *)v73 + 1);
      goto LABEL_223;
    }
    ++v73;
  }
  v74 = 0;
LABEL_223:
  dword_180075B94 = v74;
  qword_180075BA0 = (__int64)"APDU_INVALID_PARAM_OBJECT_NOT_FOUND";
  qword_180075BA8 = (__int64)"";
  qword_180075BB0 = (__int64)"INVALID: file or application not found";
  qword_180075BB8 = (__int64)"";
  v75 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075B98 = -126;
  dword_180075B9C = 4;
  dword_180075BC4 = 0;
  byte_180075BC0 = 106;
  while ( v75 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v75 == 106 )
    {
      v76 = *((_DWORD *)v75 + 1);
      goto LABEL_229;
    }
    ++v75;
  }
  v76 = 0;
LABEL_229:
  dword_180075BC4 = v76;
  qword_180075BD0 = (__int64)"APDU_INVALID_PARAM_RECORD_NOT_FOUND";
  qword_180075BD8 = (__int64)"";
  qword_180075BE0 = (__int64)"INVALID: record not found";
  qword_180075BE8 = (__int64)"";
  v77 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075BC8 = -125;
  dword_180075BCC = 4;
  dword_180075BF4 = 0;
  byte_180075BF0 = 106;
  while ( v77 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v77 == 106 )
    {
      v78 = *((_DWORD *)v77 + 1);
      goto LABEL_235;
    }
    ++v77;
  }
  v78 = 0;
LABEL_235:
  dword_180075BF4 = v78;
  qword_180075C00 = (__int64)"APDU_INVALID_PARAM_NO_SPACE_IN_FILE";
  qword_180075C08 = (__int64)"";
  qword_180075C10 = (__int64)"INVALID: not enough memory space in the file";
  qword_180075C18 = (__int64)"";
  v79 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075BF8 = -124;
  dword_180075BFC = 4;
  dword_180075C24 = 0;
  byte_180075C20 = 106;
  while ( v79 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v79 == 106 )
    {
      v80 = *((_DWORD *)v79 + 1);
      goto LABEL_241;
    }
    ++v79;
  }
  v80 = 0;
LABEL_241:
  dword_180075C24 = v80;
  qword_180075C30 = (__int64)"APDU_INVALID_PARAM_DATA_TLV_LENGTH";
  qword_180075C38 = (__int64)"";
  qword_180075C40 = (__int64)"INVALID: data field length does not match TLV structure lengths";
  qword_180075C48 = (__int64)"";
  v81 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075C28 = -123;
  dword_180075C2C = 4;
  dword_180075C54 = 0;
  byte_180075C50 = 106;
  while ( v81 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v81 == 106 )
    {
      v82 = *((_DWORD *)v81 + 1);
      goto LABEL_247;
    }
    ++v81;
  }
  v82 = 0;
LABEL_247:
  dword_180075C54 = v82;
  qword_180075C60 = (__int64)"APDU_INVALID_PARAM";
  qword_180075C68 = (__int64)"";
  qword_180075C70 = (__int64)"INVALID: incorrect parameters P1=%P1% P2=%P2%";
  qword_180075C78 = (__int64)"";
  v83 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075C58 = -122;
  dword_180075C5C = 4;
  dword_180075C84 = 0;
  byte_180075C80 = 106;
  while ( v83 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v83 == 106 )
    {
      v84 = *((_DWORD *)v83 + 1);
      goto LABEL_253;
    }
    ++v83;
  }
  v84 = 0;
LABEL_253:
  dword_180075C84 = v84;
  qword_180075C90 = (__int64)"APDU_INVALID_PARAM_DATA_LENGTH";
  qword_180075C98 = (__int64)"";
  qword_180075CA0 = (__int64)"INVALID: data field length invalid for P1=%P1% P2=%P2%";
  qword_180075CA8 = (__int64)"";
  v85 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075C88 = -121;
  dword_180075C8C = 4;
  dword_180075CB4 = 0;
  byte_180075CB0 = 106;
  while ( v85 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v85 == 106 )
    {
      v86 = *((_DWORD *)v85 + 1);
      goto LABEL_259;
    }
    ++v85;
  }
  v86 = 0;
LABEL_259:
  dword_180075CB4 = v86;
  qword_180075CC0 = (__int64)"APDU_INVALID_PARAM_REFERENCE_NOT_FOUND";
  qword_180075CC8 = (__int64)"";
  qword_180075CD0 = (__int64)"INVALID: referenced data not found or reference data not found";
  qword_180075CD8 = (__int64)"";
  v87 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075CB8 = -120;
  dword_180075CBC = 4;
  dword_180075CE4 = 0;
  byte_180075CE0 = 106;
  while ( v87 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v87 == 106 )
    {
      v88 = *((_DWORD *)v87 + 1);
      goto LABEL_265;
    }
    ++v87;
  }
  v88 = 0;
LABEL_265:
  dword_180075CE4 = v88;
  qword_180075CF0 = (__int64)"APDU_INVALID_PARAM_FILE_EXISTS";
  qword_180075CF8 = (__int64)"";
  qword_180075D00 = (__int64)"INVALID: file already exists";
  qword_180075D08 = (__int64)"";
  v89 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075CE8 = -119;
  dword_180075CEC = 4;
  dword_180075D14 = 0;
  byte_180075D10 = 106;
  while ( v89 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v89 == 106 )
    {
      v90 = *((_DWORD *)v89 + 1);
      goto LABEL_271;
    }
    ++v89;
  }
  v90 = 0;
LABEL_271:
  dword_180075D14 = v90;
  qword_180075D20 = (__int64)"APDU_INVALID_PARAM_DIRECTORY_EXISTS";
  qword_180075D28 = (__int64)"";
  qword_180075D30 = (__int64)"INVALID: directory file already exists";
  qword_180075D38 = (__int64)"";
  v91 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075D18 = -118;
  dword_180075D1C = 4;
  dword_180075D44 = 0;
  byte_180075D40 = 107;
  while ( v91 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v91 == 107 )
    {
      v92 = *((_DWORD *)v91 + 1);
      goto LABEL_277;
    }
    ++v91;
  }
  v92 = 0;
LABEL_277:
  dword_180075D44 = v92;
  qword_180075D50 = (__int64)"APDU_INVALID_PARAMETERS";
  qword_180075D58 = (__int64)"";
  qword_180075D60 = (__int64)"INVALID: Wrong parameters P1=%P1% P2=%P2%";
  qword_180075D68 = (__int64)"";
  v93 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075D48 = 0;
  dword_180075D4C = 2;
  dword_180075D74 = 0;
  byte_180075D70 = 108;
  while ( v93 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v93 == 108 )
    {
      v94 = *((_DWORD *)v93 + 1);
      goto LABEL_283;
    }
    ++v93;
  }
  v94 = 0;
LABEL_283:
  dword_180075D74 = v94;
  qword_180075D80 = (__int64)"APDU_INVALID_MAX_RESPONSE_SIZE";
  qword_180075D88 = (__int64)"";
  qword_180075D90 = (__int64)"INVALID: command.maximumResponseSize field invalid should be: SW2=%SW2%";
  qword_180075D98 = (__int64)"";
  v95 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075D78 = 0;
  dword_180075D7C = 3;
  dword_180075DA4 = 0;
  byte_180075DA0 = 109;
  while ( v95 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v95 == 109 )
    {
      v96 = *((_DWORD *)v95 + 1);
      goto LABEL_289;
    }
    ++v95;
  }
  v96 = 0;
LABEL_289:
  dword_180075DA4 = v96;
  qword_180075DB0 = (__int64)"APDU_INVALID_OR_UNSUPPORTED_INS";
  qword_180075DB8 = (__int64)"";
  qword_180075DC0 = (__int64)"INVALID: INS not supported or invalid";
  qword_180075DC8 = (__int64)"";
  v97 = `ProcessField::make'::`2'::sw1fieldmap;
  byte_180075DA8 = 0;
  dword_180075DAC = 2;
  dword_180075DD4 = 0;
  byte_180075DD0 = 110;
  while ( v97 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v97 == 110 )
    {
      v98 = *((_DWORD *)v97 + 1);
      goto LABEL_295;
    }
    ++v97;
  }
  v98 = 0;
LABEL_295:
  dword_180075DD4 = v98;
  qword_180075DE0 = (__int64)"APDU_INVALID_CLASS_NOT_SUPPORTED";
  qword_180075DE8 = (__int64)"";
  qword_180075DF0 = (__int64)"INVALID: Class not supported";
  qword_180075DF8 = (__int64)"";
  byte_180075DD8 = 0;
  dword_180075DDC = 2;
  dword_180075E04 = 0;
  byte_180075E00 = 111;
  while ( v0 != (__int64 *)"NULL" )
  {
    if ( *(_BYTE *)v0 == 111 )
    {
      v99 = *((_DWORD *)v0 + 1);
      goto LABEL_301;
    }
    ++v0;
  }
  v99 = 0;
LABEL_301:
  dword_180075E04 = v99;
  qword_180075E10 = (__int64)"APDU_INVALID_UNSPECIFIED";
  qword_180075E18 = (__int64)"";
  qword_180075E20 = (__int64)"INVALID: Unspecified failure";
  result = "";
  qword_180075E28 = (__int64)"";
  byte_180075E08 = 0;
  dword_180075E0C = 2;
  return result;
}

```

## disassembly

```asm
0x180001130  push    rbx
0x180001132  push    rsi
0x180001133  push    rdi
0x180001134  lea     rdx, ?sw1fieldmap@?1??make@ProcessField@@SA?AW4type@2@E@Z@4QBUSW1FieldMap@?1??12@SA?AW432@E@Z@B; `ProcessField::make(uchar)'::`2'::SW1FieldMap const near * const `ProcessField::make(uchar)'::`2'::sw1fieldmap
0x18000113b  mov     r10d, 8
0x180001141  mov     rax, rdx
0x180001144  lea     r11, aNull; "NULL"
0x18000114b  xor     r8d, r8d
0x18000114e  cmp     rax, r11
0x180001151  jz      short loc_180001162
0x180001153  cmp     byte ptr [rax], 90h
0x180001156  jz      short loc_18000115D
0x180001158  add     rax, r10
0x18000115b  jmp     short loc_18000114B
0x18000115d  mov     ecx, [rax+4]
0x180001160  jmp     short loc_180001165
0x180001162  mov     ecx, r8d
0x180001165  lea     rax, aApduSuccess; "APDU_SUCCESS"
0x18000116c  mov     cs:dword_1800754D4, ecx
0x180001172  mov     qword ptr cs:xmmword_1800754E0, rax
0x180001179  mov     esi, 2
0x18000117e  lea     rax, aApduSuccess+0Ch; ""
0x180001185  mov     cs:byte_1800754D8, r8b
0x18000118c  mov     qword ptr cs:xmmword_1800754E0+8, rax
0x180001193  lea     rax, aSuccess; "Success:"
0x18000119a  mov     qword ptr cs:xmmword_1800754F0, rax
0x1800011a1  lea     rax, aSuccess+8; ""
0x1800011a8  mov     qword ptr cs:xmmword_1800754F0+8, rax
0x1800011af  mov     rax, rdx
0x1800011b2  mov     cs:dword_1800754DC, esi
0x1800011b8  mov     cs:dword_180075504, r8d
0x1800011bf  mov     cs:byte_180075500, 61h ; 'a'
0x1800011c6  cmp     rax, r11
0x1800011c9  jz      short loc_1800011DA
0x1800011cb  cmp     byte ptr [rax], 61h ; 'a'
0x1800011ce  jz      short loc_1800011D5
0x1800011d0  add     rax, r10
0x1800011d3  jmp     short loc_1800011C6
0x1800011d5  mov     ecx, [rax+4]
0x1800011d8  jmp     short loc_1800011DD
0x1800011da  mov     ecx, r8d
0x1800011dd  lea     rax, aApduSuccessMor; "APDU_SUCCESS_MORE_DATA"
0x1800011e4  mov     cs:dword_180075504, ecx
0x1800011ea  mov     cs:qword_180075510, rax
0x1800011f1  mov     r9b, 62h ; 'b'
0x1800011f4  lea     rax, aApduSuccessMor+16h; ""
0x1800011fb  mov     cs:byte_180075508, r8b
0x180001202  mov     cs:qword_180075518, rax
0x180001209  lea     rax, aSuccessMoreDat; "Success: more data available value=%SW2"...
0x180001210  mov     cs:qword_180075520, rax
0x180001217  lea     rax, aSuccessMoreDat+28h; ""
0x18000121e  mov     cs:qword_180075528, rax
0x180001225  mov     rax, rdx
0x180001228  mov     cs:dword_18007550C, 3
0x180001232  mov     cs:dword_180075534, r8d
0x180001239  mov     cs:byte_180075530, r9b
0x180001240  cmp     rax, r11
0x180001243  jz      short loc_180001254
0x180001245  cmp     [rax], r9b
0x180001248  jz      short loc_18000124F
0x18000124a  add     rax, r10
0x18000124d  jmp     short loc_180001240
0x18000124f  mov     ecx, [rax+4]
0x180001252  jmp     short loc_180001257
0x180001254  mov     ecx, r8d
0x180001257  lea     rax, aApduWarning; "APDU_WARNING"
0x18000125e  mov     cs:dword_180075534, ecx
0x180001264  mov     cs:qword_180075540, rax
0x18000126b  mov     edi, 1
0x180001270  lea     rax, aApduWarning+0Ch; ""
0x180001277  mov     cs:byte_180075538, r8b
0x18000127e  mov     cs:qword_180075548, rax
0x180001285  lea     rax, aWarningNonVola; "Warning: non-volatile memory state not "...
0x18000128c  mov     cs:qword_180075550, rax
0x180001293  lea     rax, aWarningNonVola+42h; ""
0x18000129a  mov     cs:qword_180075558, rax
0x1800012a1  mov     rax, rdx
0x1800012a4  mov     cs:dword_18007553C, edi
0x1800012aa  mov     cs:dword_180075564, r8d
0x1800012b1  mov     cs:byte_180075560, r9b
0x1800012b8  cmp     rax, r11
0x1800012bb  jz      short loc_1800012CC
0x1800012bd  cmp     [rax], r9b
0x1800012c0  jz      short loc_1800012C7
0x1800012c2  add     rax, r10
0x1800012c5  jmp     short loc_1800012B8
0x1800012c7  mov     ecx, [rax+4]
0x1800012ca  jmp     short loc_1800012CF
0x1800012cc  mov     ecx, r8d
0x1800012cf  lea     rax, aApduWarningCor; "APDU_WARNING_CORRUPTED_RESULT"
0x1800012d6  mov     cs:dword_180075564, ecx
0x1800012dc  mov     cs:qword_180075570, rax
0x1800012e3  mov     ebx, 4
0x1800012e8  lea     rax, aApduWarningCor+1Dh; ""
0x1800012ef  mov     cs:byte_180075568, 81h
0x1800012f6  mov     cs:qword_180075578, rax
0x1800012fd  lea     rax, aWarningReturne; "Warning: returned data may be corrupt"
0x180001304  mov     cs:qword_180075580, rax
0x18000130b  lea     rax, aWarningReturne+25h; ""
0x180001312  mov     cs:qword_180075588, rax
0x180001319  mov     rax, rdx
0x18000131c  mov     cs:dword_18007556C, ebx
0x180001322  mov     cs:dword_180075594, r8d
0x180001329  mov     cs:byte_180075590, r9b
0x180001330  cmp     rax, r11
0x180001333  jz      short loc_180001344
0x180001335  cmp     [rax], r9b
0x180001338  jz      short loc_18000133F
0x18000133a  add     rax, r10
0x18000133d  jmp     short loc_180001330
0x18000133f  mov     ecx, [rax+4]
0x180001342  jmp     short loc_180001347
0x180001344  mov     ecx, r8d
0x180001347  lea     rax, aApduWarningUne; "APDU_WARNING_UNEXPECTED_END"
0x18000134e  mov     cs:dword_180075594, ecx
0x180001354  mov     cs:qword_1800755A0, rax
0x18000135b  lea     rax, aApduWarningUne+1Bh; ""
0x180001362  mov     cs:qword_1800755A8, rax
0x180001369  lea     rax, aWarningEndOfFi; "Warning: end of file or record reached "...
0x180001370  mov     cs:qword_1800755B0, rax
0x180001377  lea     rax, aWarningEndOfFi+66h; ""
0x18000137e  mov     cs:qword_1800755B8, rax
0x180001385  mov     rax, rdx
0x180001388  mov     cs:byte_180075598, 82h
0x18000138f  mov     cs:dword_18007559C, ebx
0x180001395  mov     cs:dword_1800755C4, r8d
0x18000139c  mov     cs:byte_1800755C0, r9b
0x1800013a3  cmp     rax, r11
0x1800013a6  jz      short loc_1800013B7
0x1800013a8  cmp     [rax], r9b
0x1800013ab  jz      short loc_1800013B2
0x1800013ad  add     rax, r10
0x1800013b0  jmp     short loc_1800013A3
0x1800013b2  mov     ecx, [rax+4]
0x1800013b5  jmp     short loc_1800013BA
0x1800013b7  mov     ecx, r8d
0x1800013ba  lea     rax, aApduWarningSel_0; "APDU_WARNING_SELECTED_FILE_DEACTIVATED"
0x1800013c1  mov     cs:dword_1800755C4, ecx
0x1800013c7  mov     cs:qword_1800755D0, rax
0x1800013ce  lea     rax, aApduWarningSel_0+26h; ""
0x1800013d5  mov     cs:qword_1800755D8, rax
0x1800013dc  lea     rax, aWarningSelecte; "Warning: selected file deactivated"
0x1800013e3  mov     cs:qword_1800755E0, rax
0x1800013ea  lea     rax, aWarningSelecte+22h; ""
0x1800013f1  mov     cs:qword_1800755E8, rax
0x1800013f8  mov     rax, rdx
0x1800013fb  mov     cs:byte_1800755C8, 83h
0x180001402  mov     cs:dword_1800755CC, ebx
0x180001408  mov     cs:dword_1800755F4, r8d
0x18000140f  mov     cs:byte_1800755F0, r9b
0x180001416  cmp     rax, r11
0x180001419  jz      short loc_18000142A
0x18000141b  cmp     [rax], r9b
0x18000141e  jz      short loc_180001425
0x180001420  add     rax, r10
0x180001423  jmp     short loc_180001416
0x180001425  mov     ecx, [rax+4]
0x180001428  jmp     short loc_18000142D
0x18000142a  mov     ecx, r8d
0x18000142d  lea     rax, aApduWarningFci; "APDU_WARNING_FCI_CORRUPTED"
0x180001434  mov     cs:dword_1800755F4, ecx
0x18000143a  mov     cs:qword_180075600, rax
0x180001441  lea     rax, aApduWarningFci+1Ah; ""
0x180001448  mov     cs:qword_180075608, rax
0x18000144f  lea     rax, aWarningFileCon; "Warning: file control information not c"...
0x180001456  mov     cs:qword_180075610, rax
0x18000145d  lea     rax, aWarningFileCon+39h; ""
0x180001464  mov     cs:qword_180075618, rax
0x18000146b  mov     rax, rdx
0x18000146e  mov     cs:byte_1800755F8, 84h
0x180001475  mov     cs:dword_1800755FC, ebx
0x18000147b  mov     cs:dword_180075624, r8d
0x180001482  mov     cs:byte_180075620, r9b
0x180001489  cmp     rax, r11
0x18000148c  jz      short loc_18000149D
0x18000148e  cmp     [rax], r9b
0x180001491  jz      short loc_180001498
0x180001493  add     rax, r10
0x180001496  jmp     short loc_180001489
0x180001498  mov     ecx, [rax+4]
0x18000149b  jmp     short loc_1800014A0
0x18000149d  mov     ecx, r8d
0x1800014a0  lea     rax, aApduWarningSel; "APDU_WARNING_SELECTED_FILE_TERMINATED"
0x1800014a7  mov     cs:dword_180075624, ecx
0x1800014ad  mov     cs:qword_180075630, rax
0x1800014b4  lea     rax, aApduWarningSel+25h; ""
0x1800014bb  mov     cs:qword_180075638, rax
0x1800014c2  lea     rax, aWarningSelecte_0; "Warning: selected file in termination s"...
0x1800014c9  mov     cs:qword_180075640, rax
0x1800014d0  lea     rax, aWarningSelecte_0+2Bh; ""
0x1800014d7  mov     cs:qword_180075648, rax
0x1800014de  mov     rax, rdx
0x1800014e1  mov     cs:byte_180075628, 85h
0x1800014e8  mov     cs:dword_18007562C, ebx
0x1800014ee  mov     cs:dword_180075654, r8d
0x1800014f5  mov     cs:byte_180075650, r9b
0x1800014fc  cmp     rax, r11
0x1800014ff  jz      short loc_180001510
0x180001501  cmp     [rax], r9b
0x180001504  jz      short loc_18000150B
0x180001506  add     rax, r10
0x180001509  jmp     short loc_1800014FC
0x18000150b  mov     ecx, [rax+4]
0x18000150e  jmp     short loc_180001513
0x180001510  mov     ecx, r8d
0x180001513  lea     rax, aApduWarningNoI; "APDU_WARNING_NO_INPUT_AVAILABLE"
0x18000151a  mov     cs:dword_180075654, ecx
0x180001520  mov     cs:qword_180075660, rax
0x180001527  mov     r9b, 63h ; 'c'
0x18000152a  lea     rax, aApduWarningNoI+1Fh; ""
0x180001531  mov     cs:byte_180075658, 86h
0x180001538  mov     cs:qword_180075668, rax
0x18000153f  lea     rax, aWarningNoInput; "Warning: no input data available from a"...
0x180001546  mov     cs:qword_180075670, rax
0x18000154d  lea     rax, aWarningNoInput+3Ah; ""
0x180001554  mov     cs:qword_180075678, rax
0x18000155b  mov     rax, rdx
0x18000155e  mov     cs:dword_18007565C, ebx
0x180001564  mov     cs:dword_180075684, r8d
0x18000156b  mov     cs:byte_180075680, r9b
0x180001572  cmp     rax, r11
0x180001575  jz      short loc_180001586
0x180001577  cmp     [rax], r9b
0x18000157a  jz      short loc_180001581
0x18000157c  add     rax, r10
0x18000157f  jmp     short loc_180001572
0x180001581  mov     ecx, [rax+4]
0x180001584  jmp     short loc_180001589
0x180001586  mov     ecx, r8d
0x180001589  lea     rax, aApduWarningChg; "APDU_WARNING_CHG"
0x180001590  mov     cs:dword_180075684, ecx
0x180001596  mov     cs:qword_180075690, rax
0x18000159d  lea     rax, aApduWarningChg+10h; ""
0x1800015a4  mov     cs:qword_180075698, rax
0x1800015ab  lea     rax, aWarningNonVola_0; "Warning: non-volatile memory state chan"...
0x1800015b2  mov     cs:qword_1800756A0, rax
0x1800015b9  lea     rax, aWarningNonVola_0+3Eh; ""
0x1800015c0  mov     cs:qword_1800756A8, rax
0x1800015c7  mov     rax, rdx
0x1800015ca  mov     cs:byte_180075688, r8b
0x1800015d1  mov     cs:dword_18007568C, edi
0x1800015d7  mov     cs:dword_1800756B4, r8d
0x1800015de  mov     cs:byte_1800756B0, r9b
0x1800015e5  cmp     rax, r11
0x1800015e8  jz      short loc_1800015F9
0x1800015ea  cmp     [rax], r9b
0x1800015ed  jz      short loc_1800015F4
0x1800015ef  add     rax, r10
0x1800015f2  jmp     short loc_1800015E5
0x1800015f4  mov     ecx, [rax+4]
0x1800015f7  jmp     short loc_1800015FC
0x1800015f9  mov     ecx, r8d
0x1800015fc  lea     rax, aApduWarningChg_0; "APDU_WARNING_CHG_FILE_FULL"
0x180001603  mov     cs:dword_1800756B4, ecx
0x180001609  mov     cs:qword_1800756C0, rax
0x180001610  lea     rax, aApduWarningChg_0+1Ah; ""
0x180001617  mov     cs:qword_1800756C8, rax
0x18000161e  lea     rax, aWarningFileFil; "Warning: file filled up by last write"
0x180001625  mov     cs:qword_1800756D0, rax
0x18000162c  lea     rax, aWarningFileFil+25h; ""
0x180001633  mov     cs:qword_1800756D8, rax
0x18000163a  mov     rax, rdx
0x18000163d  mov     cs:byte_1800756B8, 81h
0x180001644  mov     cs:dword_1800756BC, ebx
0x18000164a  mov     cs:dword_1800756E4, r8d
0x180001651  mov     cs:byte_1800756E0, r9b
0x180001658  cmp     rax, r11
0x18000165b  jz      short loc_18000166C
0x18000165d  cmp     [rax], r9b
0x180001660  jz      short loc_180001667
0x180001662  add     rax, r10
0x180001665  jmp     short loc_180001658
0x180001667  mov     ecx, [rax+4]
0x18000166a  jmp     short loc_18000166F
0x18000166c  mov     ecx, r8d
0x18000166f  lea     rax, aApduWarningChg_1; "APDU_WARNING_CHG_COUNTER"
0x180001676  mov     cs:dword_1800756E4, ecx
0x18000167c  mov     cs:qword_1800756F0, rax
0x180001683  mov     r9b, 64h ; 'd'
0x180001686  lea     rax, aApduWarningChg_1+18h; ""
0x18000168d  mov     cs:byte_1800756E8, 0C0h
0x180001694  mov     cs:qword_1800756F8, rax
0x18000169b  lea     rax, aWarningCommand; "Warning: command specific counter value"...
0x1800016a2  mov     cs:qword_180075700, rax
0x1800016a9  lea     rax, aWarningCommand+2Dh; ""
0x1800016b0  mov     cs:qword_180075708, rax
0x1800016b7  mov     rax, rdx
0x1800016ba  mov     cs:dword_1800756EC, 5
0x1800016c4  mov     cs:dword_180075714, r8d
0x1800016cb  mov     cs:byte_180075710, r9b
0x1800016d2  cmp     rax, r11
0x1800016d5  jz      short loc_1800016E6
0x1800016d7  cmp     [rax], r9b
0x1800016da  jz      short loc_1800016E1
0x1800016dc  add     rax, r10
0x1800016df  jmp     short loc_1800016D2
0x1800016e1  mov     ecx, [rax+4]
0x1800016e4  jmp     short loc_1800016E9
0x1800016e6  mov     ecx, r8d
0x1800016e9  lea     rax, aApduFailure; "APDU_FAILURE"
  ... truncated ...
```
